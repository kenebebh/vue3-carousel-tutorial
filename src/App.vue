<template>
  <div class="container">
    <Carousel>
      <Slide v-for="slide in 10" :key="slide">
        <img
          class="carousel__item"
          :src="`https://picsum.photos/500?${slide}`"
          width="250"
          height="250"
          :alt="`Item ${slide}`"
        />
      </Slide>

      <template #addons>
        <Navigation />
        <Pagination />
      </template>
    </Carousel>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Pagination, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  name: "Vue-3CarouselComponent",
  components: {
    Carousel,
    Slide,
    Pagination,
    Navigation,
  },
});
</script>

<style>
.container {
  width: 500px;
}

.carousel__item {
  min-height: 200px;
  width: 100%;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.carousel__slide {
  padding: 10px;
}

.carousel__prev,
.carousel__next {
  box-sizing: content-box;
}
</style>
