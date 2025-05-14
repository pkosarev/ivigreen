<script setup lang="ts">
import Navigation from '@/components/Navigation/Navigation.vue'
import Header from '@/components/Header/Header.vue'
import WhyBlock from '@/components/WhyBlock/WhyBlock.vue'
import SwiperComponent from '@/components/Swiper/SwiperComponent.vue'
import Topics from '@/components/Topics/Topics.vue'
import Bestsellers from '@/components/Bestsellers/Bestsellers.vue'
import Testimonials from '@/components/Testimonials/Testimonials.vue'
import Kits from '@/components/Kits/Kits.vue'
import Footer from '@/components/Footer/Footer.vue'

const slidesData = [
  {
    image: new URL('@/assets/slides/slide-1.png', import.meta.url).href,
    alt: 'slide-1'
  },
  {
    image: new URL('@/assets/slides/slide-2.png', import.meta.url).href,
    alt: 'slide-1'
  },
  {
    image: new URL('@/assets/slides/slide-3.png', import.meta.url).href,
    alt: 'slide-1'
  },
  {
    image: new URL('@/assets/slides/slide-4.png', import.meta.url).href,
    alt: 'slide-1'
  },
  {
    image: new URL('@/assets/slides/slide-5.png', import.meta.url).href,
    alt: 'slide-1'
  }
]

const bestsellers = [
  {
    image: new URL('@/assets/bestsellers/bestseller-1.png', import.meta.url).href,
    alt: 'bestseller',
    price: '$19.99',
    oldPrice: '$39.99',
    discount: '55% off',
    title: 'EMOTIONS FOR TEENS AND TWEENS',
    description: 'Help your teens deal with anger, fear, and anxiety. Give them tools to manage their emotional self'
  },
  {
    image: new URL('@/assets/bestsellers/bestseller-2.png', import.meta.url).href,
    alt: 'bestseller',
    price: '$19.99',
    oldPrice: '$39.99',
    discount: '55% off',
    title: 'RELATIONSHIPS FOR TEENS AND TWEENS',
    description: 'Equip your teens with the necessary self-confidence, enabling them to cultivate healthy relationship habits for their happiness'
  },
  {
    image: new URL('@/assets/bestsellers/bestseller-1.png', import.meta.url).href,
    alt: 'bestseller',
    price: '$19.99',
    oldPrice: '$39.99',
    discount: '55% off',
    title: 'EMOTIONS FOR TEENS AND TWEENS',
    description: 'Help your teens deal with anger, fear, and anxiety. Give them tools to manage their emotional self'
  }
]
</script>

<template>
  <Navigation />
  <Header />
  <WhyBlock />
  <SwiperComponent  :slides="slidesData"/>
  <Topics />
  <Bestsellers :slides="bestsellers" />
  <Testimonials />
  <Kits />
  <Footer />
</template>

<style scoped>

</style>
