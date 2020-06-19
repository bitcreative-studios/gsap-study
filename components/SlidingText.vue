<template>
  <div class="menu__item text-white" @mouseover="hide" @mouseleave="show">
    <span class="menu__item-number">05</span>
    <span class="menu__item-textwrap">
      <span class="menu__item-text" ref="text">Express</span>
    </span>
    <a class="menu__item-link">explore</a>
  </div>
</template>

<script>
import { gsap } from 'gsap'
export default {
  name: 'SlidingText',
  data() {
    return {
      animation: null,
    }
  },
  mounted() {
    const { text } = this.$refs
    this.animation = gsap.to(text, {
      y: '103%',
      duration: 0.5,
      ease: 'expo.in',
      paused: true,
    })
  },
  methods: {
    hide() {
      this.animation.play()
    },
    show() {
      this.animation.reverse()
    },
  },
}
</script>

<style scoped>
.menu__item {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  pointer-events: auto;
}
.menu__item-textwrap {
  position: relative;
  overflow: hidden;
  line-height: 1;
}

.menu__item-text {
  font-family: 'Anton', Arial, sans-serif;
  text-transform: uppercase;
  -webkit-text-stroke: 2px #fff;
  text-stroke: 2px #fff;
  -webkit-text-fill-color: transparent;
  text-fill-color: transparent;
  color: transparent;
  font-size: 2rem;
  padding: 0 1rem;
  cursor: pointer;
  display: inline-block;
}
</style>
