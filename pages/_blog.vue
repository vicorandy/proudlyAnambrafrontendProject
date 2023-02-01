<template>
  <div class="container">
    <h3>{{ blogName }}</h3>
    <div class="author-info">
      <h4>{{ authorName }}</h4>
      <p class="date">08 jan, 2023</p>
    </div>
    <div class="blog">
      <div class="img"></div>
      <p>
        <img :src="imgLink" class="img" />
        {{ blog }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    this.fetchBlog();
  },
  data() {
    return {
      blog: null,
      authorName: null,
      imgLink: null,
      blogName: null,
    };
  },
  methods: {
    async fetchBlog() {
      try {
        const id = this.$route.params.blog;
        const response = await fetch(`http://localhost:5000/blogs/${id}`);

        const data = await response.json();
        if (data.ok === false) {
          this.$router.push("/");
        }
        this.blog = data.blog.blog[0].blog;
        this.imgLink = data.blog.blog[0].imgLink;
        this.blogName = data.blog.blog[0].blogName;
        this.authorName = data.blog.authorName;
        console.log(response);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped>
.container {
  margin: 40px;
}
.img {
  float: right;
  margin: 0px 0px 15px 20px;
}
img {
  width: 300px;
  height: 300px;
  border-radius: 15px;
}

.author-info {
  display: flex;
}
.date {
  font-size: 12px;
  margin-top: 25px;
  margin-left: 90px;
  color: #989898;
}
h3 {
  margin-bottom: 0px;
}
pre {
  font-family: inherit;
}
@media only screen and (max-width: 600px) {
  img {
    width: 250px;
    height: 250px;
  }
}
@media only screen and (max-width: 500px) {
  img {
    width: 150px;
    height: 150px;
  }
}
</style>
