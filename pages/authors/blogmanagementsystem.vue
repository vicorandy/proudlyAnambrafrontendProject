<template>
  <div>
    <div class="container">
      <div class="form-container">
        <div>
          <p class="p-text">welcome back, {{ authorName }}</p>
          <p class="p-text">create your blog here</p>
        </div>
        <div>
          <input
            type="text"
            placeholder="enter name of blogPost"
            v-model="blogName"
          />
        </div>
        <div>
          <input type="text" placeholder="enter blog post" v-model="blog" />
        </div>
        <div class="form-input">
          <input
            type="text"
            placeholder="enter blog image Link"
            v-model="imgLink"
          />
        </div>
        <p v-show="errorMessage" class="error">{{ errorMessage }}</p>
        <div class="btn">
          <button v-on:click="submit">Post Blog</button>
        </div>
      </div>
    </div>

    <div class="grid" v-show="blogs">
      <div class="blog-conatiner" v-for="blg in blogs" :key="blg._id">
        <div class="blog-img">
          <img :src="blg.blog[0].imgLink" class="image" />
        </div>
        <div class="description">
          <h5>{{ blg.blog[0].blogName }}</h5>

          <select name="cars" :id="blg._id">
            <option style="display: none"></option>
            <option v-on:click="addTofeature" :id="blg._id">
              add to feature
            </option>
            <option v-on:click="removefromFeature" :id="blg._id">
              remove from feature
            </option>
            <option v-on:click="deleteAuthorBlogs" :id="blg._id">
              delete blog
            </option>
          </select>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      blog: "",
      blogName: "",
      imgLink: "",
      blogs: null,
      authorName: null,
      token: null,
      errorMessage: null,
    };
  },
  mounted() {
    this.isUserLoggedIn();
    this.fetchAuthorBlogs();
  },
  methods: {
    async submit(e) {
      e.preventDefault();
      const blogPost = {
        blog: [
          {
            blog: this.blog,
            imgLink: this.imgLink,
            blogName: this.blogName,
          },
        ],
      };
      try {
        const response = await fetch(`http://localhost:5000/blogs/createBlog`, {
          method: "POST",
          body: JSON.stringify(blogPost),
          headers: {
            "Content-Type": "application/json; charset=UTF-8",
            authorization: `Bearer ${this.token}`,
          },
        });
        const data = await response.json();
        console.log(data);
        if (data.ok === false) {
          this.errorMessage = data.message;
          return;
        }
        this.blog = this.blogName = this.imgLink = "";

        this.fetchAuthorBlogs();
      } catch (error) {
        console.log(error);
      }
    },
    isUserLoggedIn() {
      const data = JSON.parse(localStorage.getItem("author"));
      this.authorName = data.name;
      this.token = data.token;

      if (!data) {
        this.$router.push("/authors/login");
        return;
      }
    },
    async fetchAuthorBlogs() {
      const response = await fetch(`http://localhost:5000/blogs/authorblogs`, {
        method: "GET",
        headers: {
          "Content-Type": "application/json",
          authorization: `Bearer ${this.token}`,
        },
      });
      const { data } = await response.json();
      this.blogs = data;
    },
    async deleteAuthorBlogs(e) {
      try {
        const id = e.target.id;
        console.log(id);
        const response = await fetch(`http://localhost:5000/blogs/${id}`, {
          method: "DELETE",
          headers: {
            "Content-Type": "application/json",
            authorization: `Bearer ${this.token}`,
          },
        });

        const data = await response.json();

        if (data.ok === true) {
          this.fetchAuthorBlogs();
        }
      } catch (error) {
        console.log(error);
      }
    },
    async addTofeature(e) {
      const { id } = e.target;
      const response = await fetch(
        `http://localhost:5000/blogs/addfeature/${id}`,
        {
          method: "PATCH",
        }
      );
      const data = await response.json();
    },
    async removefromFeature(e) {
      const { id } = e.target;
      const response = await fetch(
        `http://localhost:5000/blogs/removefeature/${id}`,
        {
          method: "PATCH",
        }
      );
      const data = await response.json();
    },
  },
};
</script>
<style scoped>
.container {
  margin: 40px;
  display: flex;
  justify-content: center;
}
.form-container {
  border: 1px solid black;
  box-shadow: #131212;
  padding: 55px;
  border-radius: 15px;
  width: 70%;
}
.form-nav {
  display: flex;
  flex-direction: coloum;
  justify-content: center;
  margin-bottom: 12px;
}
.form-nav div {
  padding: 6px;
  margin-left: 2px;
  cursor: pointer;
}
.p-text {
  color: #f49e0b;
}
.error {
  color: red;
}
input {
  width: 100%;
  margin-bottom: 12px;
  height: 32px;
  border: 1px solid #f49e0b;
  padding: 4px;
  border-radius: 7px;
}

.btn button {
  border-style: none;
  width: 60%;
  border-radius: 6px;
  padding: 9px 6px;
  background: #f49e0b;
  color: white;
  font-weight: bold;
}

.blog-conatiner {
  margin-top: 22px;
}
.blog-img {
  height: 130px;
  width: 230px;
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
  flex-direction: column;
  background: #d9d9d9;
  width: 205px;
  padding: 0 12px;
}
.btn {
  margin-top: 40px;
  color: white;
}
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-items: center;
}
select {
  border-style: none;
  padding: 2px;
  background-color: #807575;
  color: white;
}

@media only screen and (max-width: 1100px) {
  .grid {
    grid-template-columns: 1fr 1fr;
    justify-items: center;
  }
}
@media only screen and (max-width: 600px) {
  .blog-img {
    height: 100px;
    width: 200px;
  }
  .description {
    width: 180px;
    padding: 10px;
  }
  .grid {
    grid-template-columns: 1fr;
    justify-items: center;
  }
}
</style>
