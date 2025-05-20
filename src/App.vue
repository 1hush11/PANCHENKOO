<script setup>
  import Header from './components/Header.vue'
  import Intro from './components/Intro.vue'
  import Projects from './components/Projects.vue'
  import Details from './components/Details.vue'
  import Footer from './components/Footer.vue'

  import { onMounted } from 'vue'

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
        observer.unobserve(entry.target) // отключаем после показа (по желанию)
      }
    })
  }, {
    threshold: 0.1
  })

  document.querySelectorAll('.fade-up').forEach(el => observer.observe(el))
})
</script>

<template>
  <Header/>
  <Intro/>
  <Projects/>
  <Details/>
  <Footer/>
</template>

<style scoped>

</style>
