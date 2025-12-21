<template>
  <section id="footer" class="bg-charcoal">
    <div class="container max-w-6xl mx-auto flex flex-col px-4 py-4">
      <!-- logo + social -->
      <div
        class="flex flex-col space-y-6 md:space-y-0 md:flex-row border-b-2 border-bg pt-4 pb-8 md:py-8"
      >
        <div class="md:w-1/2 flex items-center justify-center md:justify-start">
          <a href="#home">
            <img src="../assets/logoWhite.svg" alt="zara wedding logo" class="h-30 w-auto -my-8" />
          </a>
        </div>

        <div
          class="md:w-1/2 flex space-x-8 md:space-x-12 justify-center md:justify-end items-center"
        >
          <a href="https://www.tiktok.com/@zara.wedding.cont" target="_blank">
            <img
              src="../assets/tiktokWhite.svg"
              alt="tiktok logo"
              class="h-8 md:h-10 w-auto hover:scale-110 duration-200"
            />
          </a>
          <a href="https://www.instagram.com/zara_wedding_creator" target="_blank">
            <img
              src="../assets/igWhite.svg"
              alt="instagram logo"
              class="h-8 md:h-10 w-auto hover:scale-110 duration-200"
            />
          </a>
          <a
            href="https://www.facebook.com/people/Zara-wedding-creator/61572916151250/"
            target="_blank"
          >
            <img
              src="../assets/fbWhite.svg"
              alt="facebook logo"
              class="h-8 md:h-10 w-auto hover:scale-110 duration-200"
            />
          </a>
        </div>
      </div>

      <!-- copyright + creator -->
      <div class="text-center py-6">
        <p class="text-bg text-sm md:text-md font-source font-semibold italic tracking-wide">
          &copy; Copyright {{ currentYear }}. Stworzone przez:
          <a
            href="https://www.marcinkosinski.dev/"
            target="_blank"
            class="underline hover:text-[#c1f2b0] transition-colors underline-offset-2"
            >Marcin Kosiński</a
          >.
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
const currentYear = new Date().getFullYear()
</script>

<style scoped></style>
