<template>
  <div class="carousel">
    <div class="carousel-inner">
      <featurecarousel-indicator
        :total="slides.length"
        :current-index="currentSlide"
      ></featurecarousel-indicator>
      <featurecarousel-items
        v-for="(slide, index) in slides"
        :slide="slide"
        :key="`item-${index}`"
        :current-slide="currentSlide"
        :index="index"
      ></featurecarousel-items>
    </div>
  </div>
</template>
<script>
import FeaturecarouselItems from "./FeaturecarouselItems.vue";
import FeaturecarouselIndicator from "./FeaturecarouselIndicator.vue";
export default {
  components: {
    FeaturecarouselItems,
    FeaturecarouselIndicator,
  },
  props: ["slides"],
  data() {
    return {
      currentSlide: 0,
      slideInterval: null,
    };
  },
  methods: {
    setCurrentSlide(index) {
      this.currentSlide = index;
    },
  },
  mounted() {
    this.slideInterval = setInterval(() => {
      const index =
        this.currentSlide < this.slides.length - 1 ? this.currentSlide + 1 : 0;
      this.setCurrentSlide(index);
    }, 3000);
  },
  beforeMount() {
    clearInterval(this.slideInterval);
  },
};
</script>
<style scoped>
.carousel {
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
}
.carousel-inner {
  position: relative;
  width: 1096px;
  height: 486px;
  overflow: hidden;
  border-radius: 21px;
  object-fit: contain;
}

@media only screen and (max-width: 600px) {
  .carousel-inner {
    position: relative;
    width: 100%;
    height: 190px;
    overflow: hidden;
    border-radius: 21px;
  }
}
</style>
