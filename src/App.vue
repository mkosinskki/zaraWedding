<script setup>
import { RouterView } from 'vue-router'
import Home from '../src/views/Home.vue'
import AboutUs from './views/AboutUs.vue'
import Opinions from './views/Opinions.vue'
import Contact from './views/Contact.vue'
import Navbar from '../src/components/Navbar.vue'
import Footer from '../src/components/Footer.vue'
</script>

<template>
  <Navbar />

  <Home />

  <AboutUs />

  <Opinions />

  <Contact />

  <Footer />

  <RouterView />
</template>

<style scoped></style>
