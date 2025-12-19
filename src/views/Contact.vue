<template>
  <section id="contact" class="relative py-16 px-6">
    <div
      class="absolute inset-0 bg-[url(../assets/contactPhoto.jpg)] bg-cover bg-center opacity-20 -z-10"
    ></div>

    <div class="container mx-auto max-w-6xl flex flex-col space-y-16">
      <h2 class="font-playfair font-bold italic text-4xl md:text-5xl text-center text-charcoal">
        Skontaktuj się z nami
      </h2>

      <div class="flex flex-col items-center mx-auto space-y-8 font-source">
        <component
          :is="item.link ? 'a' : 'div'"
          v-for="(item, index) in contactForm"
          :key="index"
          :href="item.link"
          :target="item.link?.startsWith('http') ? '_blank' : undefined"
          class="flex items-center space-x-6 group w-full transition-all duration-300"
          :class="{
            'cursor-pointer': item.link,
            'hover:translate-x-2': item.link,
            'cursor-default': !item.link,
          }"
        >
          <div class="w-10 h-10 flex items-center justify-center">
            <img
              :src="item.icon"
              :alt="item.socialName"
              class="w-full h-full transition-transform duration-300"
              :class="{ 'group-hover:scale-110': item.link }"
            />
          </div>

          <div class="flex flex-col">
            <span class="text-[10px] uppercase tracking-[0.2em] text-navy/50 font-bold">
              {{ item.socialName }}
            </span>
            <span
              class="text-lg md:text-xl font-semibold text-navy transition-colors duration-300"
              :class="{ 'group-hover:text-gold': item.link }"
            >
              {{ item.displayValue }}
            </span>
          </div>
        </component>
      </div>
    </div>
  </section>
</template>

<script setup>
import InstagramIcon from '../assets/instagram.svg'
import FacebookIcon from '../assets/facebook.svg'
import MailIcon from '../assets/mail.svg'
import PhoneIcon from '../assets/phone.svg'

const contactForm = [
  {
    socialName: 'Instagram',
    displayValue: '@zara_wedding_creator',
    link: 'https://www.instagram.com/zara_wedding_creator',
    icon: InstagramIcon,
  },
  {
    socialName: 'Facebook',
    displayValue: 'Zara wedding creator',
    link: 'https://www.facebook.com/people/Zara-wedding-creator/61572916151250/',
    icon: FacebookIcon,
  },
  {
    socialName: 'Email',
    displayValue: 'zara.creator@icloud.com',
    link: null,
    icon: MailIcon,
  },
  {
    socialName: 'Telefon',
    displayValue: '693 252 567',
    link: null,
    icon: PhoneIcon,
  },
]
</script>

<style scoped></style>
