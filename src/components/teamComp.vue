<template>
  <Carousel :items-to-show="2.5" :wrap-around="true">
    <Slide v-for="slide in 10" :key="slide">
      <div class="carousel__item">{{ slide }}</div>
    </Slide>

    <template #addons>
      <Navigation />
    </template>
  </Carousel>
  <div id="idDiv">
    hello
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import { Carousel, Navigation, Slide } from 'vue3-carousel'

import 'vue3-carousel/dist/carousel.css'

export default defineComponent({
  name: 'WrapAround',
  components: {
    Carousel,
    Slide,
    Navigation,
  },
})
</script>

<style scoped>
.carousel__item {
    height: 10vh;
    width: 10vh;
    background-color: aqua;
}

#idDiv {
    height: 30vh;
}
</style>