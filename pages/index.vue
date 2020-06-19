<template>
  <div class="min-h-screen bg-black">
    <Header />
    <div class="container mx-auto">
      <ProjectCard
        v-for="project in projects"
        :key="project.id"
        :number="project.project"
        :title="project.title"
        :image="project.img"
      />
    </div>
  </div>
</template>

<script>
import Header from '../components/Header'
import ProjectCard from '../components/ProjectCard'
export default {
  name: 'Home',
  components: { ProjectCard, Header },
  data() {
    return {
      projects: [
        {
          id: Math.random().toString(36).substr(-11),
          project: 1,
          title: `1'edition`,
          img: `${require('../assets/image/project-2.jpg')}`,
        },
      ],
    }
  },
}
</script>
