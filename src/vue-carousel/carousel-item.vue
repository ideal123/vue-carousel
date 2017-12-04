<template>
  <div class="vue-carousel-item" :style="styles">
    <slot></slot>
  </div>
</template>

<script>
export default {
  data () {
    return {
      width: 0
    }
  },
  computed: {
    styles () {
      return {
        width: `${this.width}px`
      }
    }
  }
}
</script>

<style>
 .vue-carousel-item {
   float: left;
   height: 100%;
 }
</style>
