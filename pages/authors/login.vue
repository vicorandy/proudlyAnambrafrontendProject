<template>
  <div class="container">
    <div class="form-container">
      <div class="form-nav">
        <div :class="{ active: mode === 'signUp' }" v-on:click="signUpMode">
          SignUp
        </div>
        <div :class="{ active: mode === 'signIn' }" v-on:click="signInMode">
          SignIn
        </div>
      </div>
      <div>
        <input
          type="text"
          placeholder="enter your full name"
          v-show="mode === 'signUp'"
          v-model="name"
        />
      </div>
      <div class="form-input">
        <input
          type="text"
          placeholder="enter your email address"
          v-model="email"
        />
      </div>
      <div class="form-input">
        <input
          type="text"
          placeholder="enter your password"
          v-model="password"
        />
      </div>
      <p v-show="errorMessage" class="error">{{ errorMessage }}</p>
      <div class="btn">
        <button v-on:click="submit">{{ buttonText }}</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      mode: "signUp",
      name: "",
      email: "",
      password: "",
      errorMessage: null,
    };
  },
  computed: {
    buttonText() {
      if (this.mode === "signIn") return "Sign In";
      if (this.mode === "signUp") return "Sign Up";
    },
  },
  methods: {
    signInMode() {
      this.mode = "signIn";
    },
    signUpMode() {
      this.mode = "signUp";
    },
    async submit(e) {
      e.preventDefault();
      const author = {
        name: this.name,
        email: this.email,
        password: this.password,
      };

      try {
        const url = this.mode === "signUp" ? "register" : "login";

        const response = await fetch(`http://localhost:5000/authors/${url}`, {
          method: "POST",
          body: JSON.stringify(author),
          headers: {
            "Content-Type": "application/json; charset=UTF-8",
          },
        });
        const data = await response.json();

        if (data.ok === false) {
          this.errorMessage = data.message;
          return;
        }
        if (data.ok === true) {
          localStorage.setItem("author", JSON.stringify(data));
          this.$router.push("/authors/blogmanagementsystem");
        }
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
.error {
  color: red;
}
.active {
  border-bottom: 4px solid #f49e0b;
}
.btn {
  display: flex;
  justify-content: center;
}

input {
  width: 100%;
  margin-bottom: 12px;
  height: 32px;
  border: 1px solid #f49e0b;
  padding: 4px;
  border-radius: 7px;
}

button {
  border-style: none;
  width: 60%;
  border-radius: 6px;
  padding: 9px 6px;
  background: #f49e0b;
  color: white;
  font-weight: bold;
}
</style>
