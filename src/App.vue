<script setup>
  import Header from './components/Header.vue'
  import Intro from './components/Intro.vue'
  import About from './components/About.vue'
  import Projects from './components/Projects.vue'
  import Details from './components/Details.vue'
  import Footer from './components/Footer.vue'

  import { ref, onMounted, onUnmounted } from 'vue'

const visible = ref(false)
const threshold = 200

const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

const handleScroll = () => {
  visible.value = window.pageYOffset > threshold
}

onMounted(() => {
  const observer = new IntersectionObserver((entries, obs) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('visible')
        obs.unobserve(entry.target)
      }
    })
  }, { threshold: 0.1 })

  document.querySelectorAll('.fade-up').forEach(el => {
    observer.observe(el)
  })

  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <Header/>
  <Intro/>
  <About/>
  <Projects/>
  <Details/>
  <!-- <Footer/> -->

  <button
    v-show="visible"
    @click="scrollToTop"
    class="back-to-top"
  >
    <span class="arrow-up">‹</span>
  </button>
</template>

<style scoped>
.back-to-top {
  position: fixed;
  right: 20px;
  bottom: 30px;
  border: none;
  background: rgba(17, 17, 17, 0.95);

  width: 50px;
  height: 50px;
  color: #CCC;
  border-radius: 99%;
  cursor: pointer;
  transition: opacity 0.3s;
}

.back-to-top[style*="display: none"] {
  opacity: 0;
}

.arrow-up {
  display: inline-block;
  transform-origin: center center;
  transform: rotate(90deg);
  font-size: 2em;
  line-height: 1;
}
</style>
