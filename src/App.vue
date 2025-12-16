<script setup>
import { RouterView } from 'vue-router'
import Navbar from '../src/components/Navbar.vue'
import Footer from '../src/components/Footer.vue'
</script>

<template>
  <Navbar />

  <Footer />

  <RouterView />
</template>

<style scoped></style>
