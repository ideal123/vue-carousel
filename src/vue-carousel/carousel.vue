<template>
  <div class="vue-carousel">
    <div class="vue-carousel-wrap" :style="styles">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    autoSpeed: {
      type: Number,
      default: 2000
    }
  },
  data () {
    return {
      pos: 0,
      width: 0,
      trackWidth: 0
    }
  },
  computed: {
    styles () {
      return {
        width: `${this.trackWidth}px`,
        transform: `translate3D(${-this.width * this.pos}px, 0, 0)`
      }
    },
    slidesLen () {
      return this.$children.length
    }
  },
  methods: {
    updateSlides () {
      this.width = parseInt(getComputedStyle(this.$el).width.replace('px', ''), 10)
      this.trackWidth = this.width * this.slidesLen

      this.$children.forEach(item => item.width = this.width)
    },
    startSlides () {
      setInterval(() => {
        this.pos = (this.pos + 1) % this.slidesLen
      }, this.autoSpeed)
    }
  },
  mounted () {
    this.updateSlides()
    this.startSlides()
  }
}
</script>

<style>
  .vue-carousel {
    overflow: hidden;
    position: relative;
    height: 200px;
  }

  .vue-carousel-wrap {
    overflow: hidden;
    height: 100%;
    transition: .3s transform;
  }
</style>


