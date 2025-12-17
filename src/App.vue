<script setup>
import { RouterView } from 'vue-router'
import Home from '../src/views/Home.vue'
import AboutUs from './views/AboutUs.vue'
import Navbar from '../src/components/Navbar.vue'
import Footer from '../src/components/Footer.vue'
</script>

<template>
  <Navbar />

  <Home />

  <AboutUs />

  <Footer />

  <RouterView />
</template>

<style scoped></style>
