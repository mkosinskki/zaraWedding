<template>
  <nav class="w-full sticky top-0 bg-bg shadow-md z-50">
    <div class="container max-w-6xl mx-auto px-5 py-5 flex items-center justify-between">
      <div class="z-50 flex items-center">
        <a href="#home" class="group relative h-12 w-32 flex items-center justify-center">
          <img
            src="../assets/logo.svg"
            alt="zara wedding logo"
            class="absolute h-30 w-auto pointer-events-none transition-transform duration-200 group-hover:scale-110"
          />
        </a>
      </div>

      <button
        id="menu-btn"
        type="button"
        class="z-50 block hamburger md:hidden focus:outline-none"
        :class="{ open: isMenuOpen }"
        @click="toggleMenu"
      >
        <span class="hamburger-top"></span>
        <span class="hamburger-middle"></span>
        <span class="hamburger-bottom"></span>
      </button>

      <div class="hidden md:flex items-center gap-4 lg:gap-12">
        <a
          v-for="item in menuItems"
          :key="item.name"
          :href="item.path"
          class="group relative text-charcoal px-1 py-1 flex justify-center items-center"
        >
          <span class="relative z-10 bg-offWhite px-2.5 rounded-sm text-lg font-source">{{
            item.name
          }}</span>

          <span
            class="absolute -bottom-0.5 left-0 h-0.5 bg-charcoal w-0 group-hover:w-full transition-all duration-300 ease-in-out"
          ></span>
        </a>
      </div>
    </div>

    <Transition name="fade">
      <div
        v-if="isMenuOpen"
        class="absolute top-full left-0 w-full bg-filler shadow-lg flex flex-col items-center py-8 space-y-6 font-bold md:hidden z-40"
      >
        <a
          v-for="item in menuItems"
          :key="item.name"
          :href="item.path"
          @click="toggleMenu"
          class="group relative text-charcoal font-normal font-source px-4 py-2 flex justify-center items-center text-xl w-full"
        >
          <span class="relative z-10 px-2.5">{{ item.name }}</span>
        </a>
      </div>
    </Transition>

    <Transition name="fade">
      <div
        v-if="isMenuOpen"
        @click="toggleMenu"
        class="fixed inset-x-0 bottom-0 top-30 -z-10 bg-black/20 backdrop-blur-sm md:hidden h-screen"
      ></div>
    </Transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const menuItems = [
  { name: 'Home', path: '#home' },
  { name: 'Oferta', path: '#offer' },
  { name: 'O nas', path: '#about' },
  { name: 'Opinie', path: '#opinions' },
  { name: 'Kontakt', path: '#contact' },
]
</script>

<style scoped>
.hamburger {
  cursor: pointer;
  width: 24px;
  height: 24px;
  transition: all 0.25s;
  position: relative;
}

.hamburger-top,
.hamburger-middle,
.hamburger-bottom {
  position: absolute;
  width: 24px;
  height: 2px;
  top: 0;
  left: 0;
  background: #2c2c2c;
  transform: rotate(0);
  transition: all 0.5s;
}

.hamburger-middle {
  transform: translateY(7px);
}

.hamburger-bottom {
  transform: translateY(14px);
}

.open {
  transform: rotate(90deg);
  transform-origin: center;
}

.open .hamburger-top {
  transform: rotate(45deg) translateY(6px) translateX(6px);
}

.open .hamburger-middle {
  display: none;
}

.open .hamburger-bottom {
  transform: rotate(-45deg) translateY(6px) translateX(-6px);
}

.fade-enter-active,
.fade-leave-active {
  transition:
    opacity 0.3s ease,
    transform 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
