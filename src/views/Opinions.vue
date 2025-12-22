<template>
  <section id="opinions" class="bg-navy py-16 px-6 overflow-hidden scroll-mt-12">
    <div class="container mx-auto max-w-7xl">
      <h2 class="text-bg text-4xl md:text-5xl font-playfair italic text-center mb-16">
        Opinie naszych klientów
      </h2>

      <div class="relative max-w-6xl mx-auto px-2 md:px-0">
        <swiper
          :modules="[SwiperNavigation, SwiperPagination, SwiperAutoplay]"
          :slides-per-view="1"
          :space-between="20"
          :autoplay="{ delay: 8000, disableOnInteraction: false }"
          :loop="true"
          :navigation="{
            prevEl: prevBtn,
            nextEl: nextBtn,
          }"
          :breakpoints="{
            '768': { slidesPerView: 3, spaceBetween: 30 },
          }"
          @swiper="onSwiperInit"
          class="opinion-swiper"
        >
          <swiper-slide v-for="(opinion, index) in opinions" :key="index" class="h-auto">
            <div
              class="bg-filler rounded-lg p-8 shadow-xl h-full flex flex-col items-center text-justify font-source"
            >
              <h3 class="text-charcoal font-bold text-xl md:text-2xl pb-1.5 font-playfair">
                {{ opinion.names }}
              </h3>
              <p class="text-navy/80 text-xs mb-6 uppercase tracking-widest">{{ opinion.date }}</p>

              <div class="text-charcoal leading-relaxed text-sm md:text-base">
                <p v-for="(line, lIdx) in opinion.text" :key="lIdx" class="mb-4 last:mb-0">
                  {{ line }}
                </p>
              </div>
            </div>
          </swiper-slide>
        </swiper>

        <button
          ref="prevBtn"
          class="prev-btn absolute left-0 md:-left-16 top-1/2 -translate-y-1/2 z-30 flex items-center justify-center w-11 h-11 rounded-full bg-white/20 md:bg-white/5 border border-white/30 text-white backdrop-blur-md md:backdrop-blur-none hover:bg-white/20 transition-all shadow-lg md:shadow-none"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
          </svg>
        </button>

        <button
          ref="nextBtn"
          class="next-btn absolute right-0 md:-right-16 top-1/2 -translate-y-1/2 z-30 flex items-center justify-center w-11 h-11 rounded-full bg-white/20 md:bg-white/5 border border-white/30 text-white backdrop-blur-md md:backdrop-blur-none hover:bg-white/20 transition-all shadow-lg md:shadow-none"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="2.5"
            stroke="currentColor"
            class="w-6 h-6"
          >
            <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import {
  Navigation as SwiperNavigation,
  Pagination as SwiperPagination,
  Autoplay as SwiperAutoplay,
} from 'swiper/modules'

import 'swiper/css'
import 'swiper/css/navigation'

const prevBtn = ref(null)
const nextBtn = ref(null)

const onSwiperInit = (swiper) => {
  setTimeout(() => {
    swiper.params.navigation.prevEl = prevBtn.value
    swiper.params.navigation.nextEl = nextBtn.value
    swiper.navigation.destroy()
    swiper.navigation.init()
    swiper.navigation.update()
  })
}

const opinions = [
  {
    names: 'Karolina & Witold',
    date: '04.2025',
    text: [
      'Bardzo dziękuję wam raz jeszcze za piękny teledysk i te wszystkie nagrane filmiki! Jest to super alternatywa dla tych którzy nie chcą długiego, kamerowanego filmu ślubnego i coś świeżego z mega nowoczesnym podejściem! Wszystkie filmiki są super, profesjonalne i szok, że nagrywane telefonem.',
    ],
  },
  {
    names: 'Karina & Krzysztof',
    date: '06.2025',
    text: [
      'Wiktoria … jesteś mistrzynią…. Znowu się popłakaliśmy …. Dziękujemy rolki są cudne. Właśnie zaczynam oglądać powolutku. Utwierdzam się w przekonaniu że to była najlepsza decyzja dedykując się na Was, jeszcze raz dziękujemy!',
    ],
  },
  {
    names: 'Patrycja & Dawid',
    date: '07.2025',
    text: [
      'Bardzo dziękujemy za tak piękny i profesjonalny materiał. Jakość na najwyższym poziomie',
    ],
  },
  {
    names: 'Aleksandra & Przemek',
    date: '09.2025',
    text: [
      'Miesiąc po ślubie obejrzeliśmy też surowe nagrania, mega dziękujemy za ich udostępnienie, cudownie było zobaczyć wszystko. Nawet życzenia można usłyszeć drugi raz!',
      'Cały pierwszy taniec, wszystkie gry i zabawy, uśmialiśmy się do nie miara',
    ],
  },
  {
    names: 'Anna & Maciej',
    date: '10.2025',
    text: [
      'Teledysk bardzo nam się podoba! Wyszedł przepięknie i idealnie oddaje klimat naszego dnia. Jeszcze raz dziękujemy za współpracę!',
    ],
  },
  {
    names: 'Anna & Krzysztof',
    date: '10.2025',
    text: [
      'Wszystko przebiegło po naszej myśli to był cudowny dzień, a rolki przepiękne jeszcze raz bardzo dziękujemy!',
    ],
  },
]
</script>

<style scoped>
.opinion-swiper :deep(.swiper-slide) {
  height: auto;
  display: flex;
}
</style>
