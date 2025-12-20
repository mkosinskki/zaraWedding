<script setup>
import { RouterView } from 'vue-router'
import Home from '../src/views/Home.vue'
import Offer from './views/Offer.vue'
import AboutUs from './views/AboutUs.vue'
import Opinions from './views/Opinions.vue'
import Contact from './views/Contact.vue'
import Navbar from '../src/components/Navbar.vue'
import Footer from '../src/components/Footer.vue'
import { onMounted } from 'vue'
import Lenis from 'lenis'

onMounted(() => {
  const lenis = new Lenis({
    duration: 1.2,
    easing: (t) => Math.min(1, 1.001 - Math.pow(2, -10 * t)),
    smoothWheel: true,
  })

  function raf(time) {
    lenis.raf(time)
    requestAnimationFrame(raf)
  }

  requestAnimationFrame(raf)
})
</script>

<template>
  <Navbar />

  <Home />

  <Offer />

  <AboutUs />

  <Opinions />

  <Contact />

  <Footer />

  <RouterView />
</template>

<style>
html.lenis,
html.lenis body {
  height: auto;
}

.lenis.lenis-smooth {
  scroll-behavior: auto !important;
}

.lenis.lenis-smooth [data-lenis-prevent] {
  overscroll-behavior: contain;
}

.lenis.lenis-stopped {
  overflow: hidden;
}

.lenis.lenis-scrolling iframe {
  pointer-events: none;
}
</style>
