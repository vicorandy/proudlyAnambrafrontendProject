<template>
  <div>
    <div class="carousel-indicators">
      <button
        class="carousel-indicator-item"
        :class="{ active: currentIndex === index }"
        v-for="(items, index) in total"
        :key="index"
      ></button>
    </div>
    <button class="btn btnn"><i class="pi pi-arrow-right"></i></button>
  </div>
</template>

<script>
import "primeicons/primeicons.css";
export default {
  props: ["total", "currentIndex"],
};
</script>

<style scoped>
.carousel-indicators {
  position: absolute;
  transform: translateX(-50%);
  right: 70%;
  bottom: 1.5em;
  z-index: 2;
}
.btn {
  position: absolute;
  transform: translateX(-50%);
  left: 90%;
  bottom: 1.5em;
  z-index: 2;
  color: white;
}
.carousel-indicator-item {
  width: 15px;
  height: 15px;
  border: none;
  background: #d9d9d9;
  margin: 0.2em;
  border-radius: 50%;
  cursor: pointer;
  border: #1e1e1e 1px solid;
}
.active {
  background-color: #f49e0b;
}
@media only screen and (max-width: 600px) {
  .carousel-indicators {
    left: 40%;
    right: 0;
  }
  .btn {
    right: 30%;
  }
}
</style>
