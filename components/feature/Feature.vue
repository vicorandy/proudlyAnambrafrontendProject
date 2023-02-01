<template>
  <div>
    <h3>Featured</h3>
    <div class="featured">
      <div class="feature-votes" v-for="blog in blogs" :key="blog._id">
        <div class="vote">
          <h3>{{ blog.blog[0].blogName }}</h3>
          <div class="vote-sub-sec">
            <p>post by {{ blog.authorName }}</p>
            <button class="btnn" :id="blog._id">
              <i
                class="pi pi-arrow-right"
                :id="blog._id"
                v-on:click="goToBlog"
              ></i>
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Feature",
  mounted() {
    this.fetchFeatuedBlogs();
  },
  data() {
    return {
      blogs: null,
    };
  },
  methods: {
    async fetchFeatuedBlogs() {
      try {
        const response = await fetch(`http://localhost:5000/blogs/feature`);
        const { featureBlogs } = await response.json();
        this.blogs = featureBlogs;
      } catch (error) {
        console.log(error);
      }
    },
    goToBlog(e) {
      const id = e.target.id;
      this.$router.push(`/${id}`);
    },
  },
};
</script>

<style>
.featured {
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
.feature-votes {
  display: flex;
  flex-direction: column;
  width: 487px;
  justify-content: space-between;
  margin-left: auto;
  margin-right: auto;
  margin-bottom: 22px;
}
.vote {
  width: 487px;
  left: 84px;
  top: 690px;
  border-radius: 15px;
  background: #d9d9d9;
  padding: 18px;
}

.vote-sub-sec {
  display: flex;
  justify-content: space-between;
  padding: 0 20px;
}

h3 {
  margin: 0;
  padding: 0;
}
.btnn {
  background: #1e1e1e;
  border-style: none;
  border-radius: 50%;
  padding: none;
  width: 35px;
  height: 35px;
  color: antiquewhite;
}

@media only screen and (max-width: 1150px) {
  .featured {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  .feature-votes {
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 22px;
  }
}

@media only screen and (max-width: 600px) {
  .vote {
    width: 100%;
    /* margin-right: 30px; */
  }
  .feature-votes {
    width: 90%;
    margin-left: 0px;
    margin-bottom: 22px;
  }

  button {
    margin-top: 10px;
  }
}
</style>
