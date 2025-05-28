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

  <transition name="fade">
  <button
    v-show="visible"
    @click="scrollToTop"
    class="back-to-top"
  >
    <svg fill="#FFF" width="20" height="20" viewBox="0 0 550 600">
      <path d="M460 321L426 355 262 192 98 355 64 321 262 125 460 321Z" />
    </svg>
  </button>
</transition>
</template>

<style scoped>
.back-to-top {
  position: fixed;
  right: 50px;
  bottom: 50px;
  border: none;
  background: rgba(17, 17, 17, 0.95);

  width: 50px;
  height: 50px;
  color: #CCC;
  border-radius: 99%;
  cursor: pointer;
  transition: opacity .3s ease-in-out;

  display: flex;
  justify-content: center;
  align-items: center;
}

.back-to-top[style*="display: none"] {
  opacity: 0;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.4s ease, transform 0.4s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: scale(0.7);
}

.fade-enter-to,
.fade-leave-from {
  opacity: 1;
  transform: scale(0.9);
}
</style>