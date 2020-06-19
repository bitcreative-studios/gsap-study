<template>
  <div class="min-h-screen bg-black">
    <Header />
    <div class="container mx-auto">
      <SlidingText />
    </div>
  </div>
</template>

<script>
import Header from '../components/Header'
import SlidingText from '../components/SlidingText'
export default {
  name: 'Home',
  components: { SlidingText, Header },
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
