<template>
  <section id="offer" class="relative bg-filler py-12 scroll-mt-14 md:scroll-mt-10 md:py-24 px-6">
    <div class="absolute inset-0 pointer-events-none opacity-60">
      <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
        <filter id="noise">
          <feTurbulence
            type="fractalNoise"
            baseFrequency="0.3"
            numOctaves="3"
            stitchTiles="stitch"
          />
          <feColorMatrix
            type="matrix"
            values="
            0 0 0 0 0.772
            0 0 0 0 0.627
            0 0 0 0 0.349
            0 0 0 1 0"
          />
        </filter>
        <rect width="100%" height="100%" filter="url(#noise)" />
      </svg>
    </div>

    <div
      class="relative container max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-center"
    >
      <div class="flex flex-col items-start space-y-12">
        <div class="flex flex-col text-center space-y-8">
          <h2 class="font-playfair text-charcoal font-bold italic text-4xl md:text-5xl">
            Oferta nagrań w pionie
          </h2>
          <p class="font-source text-navy text-lg md:text-xl italic">
            Dynamiczne rolki i krótki teledysk
          </p>
        </div>

        <ul class="flex flex-col space-y-4 font-source text-md md:text-xl">
          <li v-for="item in ofertaPionowa" :key="item" class="flex items-start gap-3">
            <img src="../assets/star.svg" alt="icon" class="w-4 h-4 md:w-5 md:h-5 mt-1" />
            <span class="text-charcoal">{{ item }}</span>
          </li>
        </ul>
      </div>

      <div
        class="block w-full h-0.5 my-20 md:w-0.5 md:h-auto md:mx-20 md:-my-8 md:self-stretch bg-navy/80"
      ></div>

      <div class="flex flex-col items-start space-y-12">
        <div class="flex flex-col text-center space-y-6">
          <h2 class="font-playfair text-charcoal font-bold italic text-4xl md:text-5xl">
            Oferta nagrań w poziomie
          </h2>
          <p class="font-source text-navy text-lg md:text-xl italic">
            Klasyczny teledysk nagrany telefonem, który pięknie odda klimat Waszego dnia.
          </p>
        </div>

        <ul class="flex flex-col space-y-4 font-source text-md md:text-xl">
          <li v-for="item in ofertaPozioma" :key="item" class="flex items-start gap-3">
            <img src="../assets/star.svg" alt="icon" class="w-4 h-4 md:w-5 md:h-5 mt-1" />
            <span class="text-charcoal">{{ item }}</span>
          </li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script setup>
const ofertaPionowa = [
  'Minimum 5 godzin dostępności',
  '4 zmontowane rolki',
  '1 krótki teledysk (skrót całego wydarzenia)',
  'Dojazd do 40 km w cenie',
  'Wszystkie surowe nagrania',
  'Możliwość dokupienia dodatkowych godzin',
  'Dostarczenie materiałów do 48h',
]

const ofertaPozioma = [
  'Minimum 5 godzin dostępności',
  'Teledysk ślubny (minimum 3 minuty)',
  'Dojazd do 40 km w cenie',
  'Wszystkie surowe nagrania',
  'Możliwość dokupienia nagrania rolek w pionie',
  'Możliwość dokupienia dodatkowych godzin',
  'Dostarczenie materiałów do 48h',
]
</script>

<style scoped></style>
