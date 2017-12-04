<template>
  <div id="app">
    <h1>vue-carousel</h1>
    <VueCarousel style="max-width: 500px; margin: 0 auto;">
      <VueCarouselItem class="carousel-item">1</VueCarouselItem>
      <VueCarouselItem class="carousel-item" style="background: #ccc">2</VueCarouselItem>
      <VueCarouselItem class="carousel-item">3</VueCarouselItem>
      <VueCarouselItem class="carousel-item" style="background: #ccc">4</VueCarouselItem>
    </VueCarousel>
  </div>
</template>

<script>
import { VueCarousel, VueCarouselItem } from './vue-carousel'

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    VueCarousel,
    VueCarouselItem
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1 {
  font-weight: normal;
}

.carousel-item {
  line-height: 200px;
  text-align: center;
  background: #e5e5e5;
}
</style>
