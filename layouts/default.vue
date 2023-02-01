<template>
  <div>
    <AppNavigator></AppNavigator>
    <Nuxt />
    <Footer></Footer>
  </div>
</template>
<script>
import AppNavigator from "../components/AppNavigator/AppNavigator.vue";
import Footer from "../components/footer/Footer.vue";
export default {
  components: { AppNavigator, Footer },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
body {
  padding: 0;
  margin: 0;
  background: #ffffff;
  font-family: "Poppins", system-ui, -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue",
    sans-serif;
  font-weight: 400;
  line-height: 1.75;
}
</style>
