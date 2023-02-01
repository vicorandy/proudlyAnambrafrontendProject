<template>
  <div class="container">
    <div class="img-container">
      <img src="../../assets/clientlogo.png" alt="logo" />
    </div>
    <div class="nav-container">
      <ul>
        <li><nuxt-link to="/">HOME</nuxt-link></li>
        <li><nuxt-link to="/">STORE</nuxt-link></li>
        <li><nuxt-link to="/">MORE</nuxt-link></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppNavigator",
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: space-between;
  margin-bottom: 49px;
  margin-left: 30px;
  margin-right: 30px;
  padding: 0, 34px;
}
.img-container {
  height: 68px;
  width: 175px;
  left: 117px;
  top: 58px;
}
.img-container img {
  width: inherit;
  height: inherit;
}
.nav-container {
  margin-top: 11px;
}
a {
  text-decoration: none;
  color: black;
}
ul {
  list-style: none;
  display: flex;
}

li {
  margin-left: 12px;
}
@media only screen and (max-width: 600px) {
  .img-container {
    height: 54px;
    width: 105px;
    left: 117px;
    top: 58px;
  }
  .container {
    display: flex;
    justify-content: center;
    margin-bottom: 30px;
  }
}
</style>
