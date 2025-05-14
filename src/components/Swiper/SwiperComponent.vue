<template>
  <div class="swiper-container">
    <Swiper
      :modules="modules"
      :slides-per-view="1"
      :space-between="10"
      :pagination="isMobile ? { clickable: true } : false"
      :navigation="false"
      @swiper="onSwiperInit"
      @slideChange="onSlideChange"
    >
      <swiper-slide v-for="(slide, index) in slides" :key="index">
        <img :src="slide.image" :alt="slide.alt" class="swiper-image" />
      </swiper-slide>
    </Swiper>
    <div v-if="!isMobile" class="custom-navigation">
      <button class="custom-button prev" @click="swiper?.slidePrev()">
        <svg width="18" height="20" viewBox="0 0 18 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1.28186 8.115C1.37603 8.01833 1.73161 7.605 2.06283 7.265C4.00471 5.12667 9.07047 1.62667 11.7219 0.558333C12.1245 0.386667 13.1426 0.0233333 13.6865 0C14.2077 0 14.7045 0.12 15.1786 0.363333C15.7696 0.703333 16.2437 1.23833 16.5035 1.87C16.6707 2.30833 16.9305 3.62 16.9305 3.64333C17.1903 5.07833 17.3332 7.41 17.3332 9.98667C17.3332 12.4417 17.1903 14.6783 16.9776 16.135C16.9532 16.1583 16.6935 17.7883 16.4093 18.3467C15.8881 19.3667 14.8701 20 13.7806 20H13.6865C12.9769 19.975 11.4848 19.3417 11.4848 19.3183C8.97629 18.2483 4.02744 14.92 2.03848 12.7083C2.03848 12.7083 1.47832 12.14 1.23478 11.785C0.854846 11.275 0.666504 10.6433 0.666504 10.0117C0.666504 9.30667 0.879201 8.65 1.28186 8.115Z" fill="white"/>
        </svg>
      </button>
      <button class="custom-button next" @click="swiper?.slideNext()">
        <svg width="18" height="20" viewBox="0 0 18 20" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M16.7181 8.115C16.624 8.01833 16.2684 7.605 15.9372 7.265C13.9953 5.12667 8.92953 1.62667 6.27813 0.558333C5.87547 0.386667 4.85744 0.0233333 4.31352 0C3.79234 0 3.2955 0.12 2.8214 0.363333C2.2304 0.703333 1.75629 1.23833 1.49651 1.87C1.32928 2.30833 1.06949 3.62 1.06949 3.64333C0.80971 5.07833 0.666828 7.41 0.666828 9.98667C0.666828 12.4417 0.80971 14.6783 1.02241 16.135C1.04676 16.1583 1.30654 17.7883 1.59068 18.3467C2.11187 19.3667 3.12989 20 4.21935 20H4.31352C5.02306 19.975 6.51518 19.3417 6.51518 19.3183C9.02371 18.2483 13.9726 14.92 15.9615 12.7083C15.9615 12.7083 16.5217 12.14 16.7652 11.785C17.1452 11.275 17.3335 10.6433 17.3335 10.0117C17.3335 9.30667 17.1208 8.65 16.7181 8.115Z" fill="white"/>
        </svg>
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';
import { Swiper as SwiperClass } from 'swiper/types';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Pagination, Navigation } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/pagination';
import 'swiper/css/navigation';

interface Slide {
  image: string;
  alt: string;
}

const props = defineProps<{
  slides: Slide[];
}>();

const modules = [Pagination, Navigation];
const swiper = ref<SwiperClass | null>(null);
const isMobile = ref(window.innerWidth <= 990);

const onSwiperInit = (instance: SwiperClass) => {
  swiper.value = instance;
};

const onSlideChange = () => {
  console.log('Slide changed');
};

const handleResize = () => {
  isMobile.value = window.innerWidth <= 990;
  if (swiper.value) {
    swiper.value.update();
  }
};

onMounted(() => {
  window.addEventListener('resize', handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener('resize', handleResize);
});
</script>

<style scoped>
.swiper-container {
  position: relative;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 104px;

  @media (max-width: 990px) {
    padding: 0 20px;
  }
}

.swiper {
  width: 100%;
  height: 100%;
  margin: 0 auto;
}

.swiper-image {
  width: 100%;
  border-radius: 20px !important;
}

:deep(.swiper-pagination) {
  position: static;
  margin-top: 20px;
  display: flex;
  justify-content: center;
  gap: 8px;
}

:deep(.swiper-pagination-bullet) {
  width: 12px;
  height: 12px;
  background: #32CD7A;
  opacity: .2;
  margin: 0 !important;
}

:deep(.swiper-pagination-bullet-active) {
  background: #32CD7A;
  opacity: 1;
}

.custom-navigation {
  position: absolute;
  top: 50%;
  left: 0;
  right: 0;
  transform: translateY(-50%);
  display: flex;
  justify-content: space-between;
  padding: 0 20px;
  pointer-events: none;
  z-index: 10;
}

.custom-button {
  pointer-events: auto;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  background: #32CD7A;
  border: none;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  color: #FFFFFF;
  transition: all 0.3s ease;

  &.prev {
    margin-left: 0;
  }

  &.next {
    margin-right: 0;
  }
}

@media (max-width: 990px) {
  .custom-navigation {
    display: none;
  }
}
</style>
