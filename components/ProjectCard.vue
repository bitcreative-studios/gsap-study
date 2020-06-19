<template>
  <div
    class="project-card relative text-white font-serif"
    @mouseover="expand"
    @mouseleave="shrink"
    ref="card"
  >
    <div class="relative image-container" ref="imgContainer">
      <img :src="image" class="max-w-full h-full object-cover" />
    </div>
    <h3 class="title" ref="title">{{ title }}</h3>
    <div
      class="meta flex items-center space-x-4 text-3xl absolute right-0 top-0"
      ref="meta"
    >
      <span class="prompt font-sans font-semibold" ref="prompt"
        >View project</span
      >
      <span class="divider" ref="divider" />
      <span>{{ number }}/5</span>
    </div>
  </div>
</template>

<script>
import { gsap } from 'gsap'
export default {
  name: 'ProjectCard',
  props: ['number', 'title', 'image'],
  data() {
    return {
      timeline: null,
    }
  },
  mounted() {
    const { divider, prompt, imgContainer, meta, title } = this.$refs
    this.timeline = gsap.timeline({ paused: true })
    this.timeline
      .to(imgContainer, { opacity: 0.4, scale: 0.9, duration: 0.6 })
      .to(title, { css: { left: '-30%' }, duration: 0.6 }, '<')
      .to(
        divider,
        {
          width: 200,
          duration: 0.4,
          ease: 'power2.out',
        },
        '<0.01'
      )
      .to(
        meta,
        {
          css: { right: '-12%' },
        },
        0
      )
      .to(prompt, { opacity: 1 }, '<')
  },
  methods: {
    expand() {
      this.timeline.play()
    },
    shrink() {
      this.timeline.reverse()
    },
  },
}
</script>

<style scoped>
.project-card {
  width: 650px;
  height: 680px;
}
.image-container {
  width: 100%;
  height: 680px;
  opacity: 1;
}
.title {
  @apply font-semibold absolute;
  top: 35%;
  left: -35%;
  font-size: 4.5rem;
}

.meta {
  @apply py-20;
  right: -10%;
}
.divider {
  display: inline-block;
  height: 1px;
  width: 130px;
  /*width: 260px;*/
  background: #fff;
}
.prompt {
  opacity: 0;
}
</style>
