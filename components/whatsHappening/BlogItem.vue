<template>
  <div class="blog-conatiner">
    <div class="blog-img">
      <img :src="imgLink" class="image" />
    </div>
    <div class="description">
      <h5>{{ blogName }}</h5>
      <button class="btnn btn" :id="id" v-on:click="goToBlog">
        <i class="pi pi-arrow-right" :id="id" v-on:click="goToBlog"></i>
      </button>
    </div>
  </div>
</template>

<script>
import "primeicons/primeicons.css";

export default {
  props: ["id", "blogName", "imgLink"],
  methods: {
    goToBlog(e) {
      const id = e.target.id;
      this.$router.push(`/${id}`);
    },
  },
};
</script>

<style scoped>
.blog-conatiner {
  margin-top: 22px;
}
.blog-img {
  height: 188px;
  width: 300px;
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
}
.image {
  border-top-left-radius: 15px;
  border-top-right-radius: 15px;
  width: 100%;
  height: 100%;
}
.description {
  display: flex;
  justify-content: space-evenly;
  background: #d9d9d9;
  width: 276px;
  padding: 0 12px;
}
.btn {
  margin-top: 40px;
  color: white;
}

@media only screen and (max-width: 600px) {
  .blog-img {
    height: 130px;
    width: 230px;
  }
  .description {
    width: 210px;
    padding: 10px;
  }
}
</style>
