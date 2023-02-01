<template>
  <div class="carousel-indicators">
    <button
      class="carousel-indicator-item"
      :class="{ active: currentIndex === index }"
      v-for="(items, index) in total"
      :key="index"
    ></button>
  </div>
</template>

<script>
export default {
  props: ["total", "currentIndex"],
};
</script>

<style scoped>
.carousel-indicators {
  position: absolute;
  transform: translateX(-50%);
  left: 50%;
  bottom: 1.5em;
  z-index: 2;
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
</style>
