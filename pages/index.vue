<template>
  <div class="container">
    <carousel-slide></carousel-slide>
    <feature></feature>
    <whats-happening></whats-happening>
  </div>
</template>

<script>
import CarouselSlide from "../components/carousel/CarouselSlide.vue";
import Feature from "../components/feature/Feature.vue";
import WhatsHappening from "../components/whatsHappening/WhatsHappening.vue";
export default {
  components: { CarouselSlide, Feature, WhatsHappening },
  name: "IndexPage",
};
</script>
<style scoped>
.container {
  margin: 40px;
}
</style>
