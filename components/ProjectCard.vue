<template>
  <div class="project-card relative text-white font-serif">
    <div class="image-container">
      <img :src="image" class="max-w-full h-full object-cover" />
    </div>
    <h3 class="title">{{ title }}</h3>
    <div
      class="meta flex items-center space-x-4 text-3xl absolute right-0 top-0"
    >
      <span class="prompt font-sans font-semibold">View project</span>
      <span class="divider" />
      <span>{{ number }}/5</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProjectCard',
  props: ['number', 'title', 'image'],
}
</script>

<style scoped>
.project-card {
  width: 650px;
  height: 680px;
}
.image-container {
  width: 650px;
  height: 680px;
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
