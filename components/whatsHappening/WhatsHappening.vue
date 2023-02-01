<template>
  <div class="container">
    <h3>What's Happening</h3>
    <div class="blogs-container">
      <blog-item
        v-for="blog in blogs"
        :key="blog._id"
        :id="blog._id"
        :blogName="blog.blog[0].blogName"
        :imgLink="blog.blog[0].imgLink"
      ></blog-item>
    </div>
    <div class="pagination">
      <button class="btnn icn" v-on:click="fetchPreviousPage">
        <i class="pi pi-arrow-left"></i>
      </button>
      <P class="txt">page {{ page }} of {{ pages }}</P>
      <button class="btnn icn" v-on:click="fetchNextPage">
        <i class="pi pi-arrow-right"></i>
      </button>
    </div>
  </div>
</template>

<script>
import BlogItem from "./BlogItem.vue";
import "primeicons/primeicons.css";

export default {
  created() {
    this.fetchBlogs();
  },
  components: { BlogItem },
  data() {
    return {
      page: 1,
      blogs: null,
      pages: null,
    };
  },
  methods: {
    async fetchBlogs() {
      const response = await fetch(
        `http://localhost:5000/blogs/pages/${this.page}`
      );
      const data = await response.json();
      this.blogs = data.blogs;
      this.pages = Math.ceil(data.count / 6);
      return data.blogs;
    },

    async fetchNextPage() {
      if (this.page + 1 > this.pages) return;
      this.page = this.page + 1;
      const blogs = await this.fetchBlogs();
      console.log(blogs);
      this.blogs = blogs;
    },
    async fetchPreviousPage() {
      if (this.page === 1) return;
      this.page = this.page - 1;
      const blogs = await this.fetchBlogs();
      this.blogs = blogs;
    },
  },
};
</script>

<style>
.container {
  margin-top: 20px;
}
.blogs-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-items: center;
}
.icn {
  color: white;
}
.txt {
  font-size: 13px;
  color: #989898;
  margin-left: 9px;
  margin-right: 9px;
  margin-top: 6px;
}
.pagination {
  margin-top: 15px;
  display: flex;
  justify-content: center;
}
@media only screen and (max-width: 1100px) {
  .blogs-container {
    grid-template-columns: 1fr 1fr;
    justify-items: center;
  }
}
@media only screen and (max-width: 800px) {
  .blogs-container {
    grid-template-columns: 1fr;
    justify-items: center;
  }
}
</style>
