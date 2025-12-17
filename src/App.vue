<script setup>
import { RouterView } from 'vue-router'
import Home from '../src/views/Home.vue'
import Navbar from '../src/components/Navbar.vue'
import Footer from '../src/components/Footer.vue'
</script>

<template>
  <Navbar />

  <Home />

  <Footer />

  <RouterView />
</template>

<style scoped></style>
