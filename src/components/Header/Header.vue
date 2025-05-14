<template>
  <header class="header">
  <div class="container header-container">
    <div class="left-side">
      <h1 class="title">
        Social-Emotional Learning Toolkits and Soft Skills for Educators
      </h1>
      <h3 class="text">
        Fostering emotional intelligence and progressive mindset in teen students
      </h3>
      <Button
        variant="primary"
        size="medium"
        v-if="isScreenSmall"
      >
        Show all kits
      </Button>
    </div>
    <div class="right-side">
      <img src="../../assets/tablets.png" alt="tablets">
      <ul>
        <li>Engaging activities for classroom and home use</li>
        <li>Ready-to-use materials for SEL classes</li>
        <li>Comprehensive guidelines for educators</li>
      </ul>
      <Button
        variant="primary"
        size="large"
        full-width
        v-if="isScreenLarge"
      >
        Show all kits
      </Button>
    </div>
  </div>
  </header>
</template>

<script setup lang="ts">
import Button from '@/components/Button/Button.vue'

import { ref, onMounted, onBeforeUnmount } from 'vue';

const isScreenLarge = ref<boolean>(false);
const isScreenSmall = ref<boolean>(false);

const updateScreenSize = (): void => {
  isScreenLarge.value = window.innerWidth < 990;
  isScreenSmall.value = window.innerWidth >= 990;
};

onMounted((): void => {
  updateScreenSize();
  window.addEventListener('resize', updateScreenSize);
});

onBeforeUnmount((): void => {
  window.removeEventListener('resize', updateScreenSize);
});
</script>

<style scoped>
.header {
  background-color: #3E468F;
  color: #FFFFFF;
}
.header-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 3rem 1rem;
  @media (min-width: 990px) {
    flex-direction: row;
  }
}
.title {
  font-weight: 700;
  font-size: 28px;
  line-height: 120%;
  max-width: 343px;
  text-transform: uppercase;
  margin-bottom: 16px;
  @media (min-width: 990px) {
    max-width: 509px;
    font-size: 40px;
  }
}
.text {
  font-weight: 500;
  font-size: 16px;
  line-height: 150%;
  margin-bottom: 24px;
  @media (min-width: 990px) {
    font-size: 28px;
  }
}
.right-side {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  @media (min-width: 990px) {
    width: auto;
    position: relative;
  }
  img {
    object-fit: contain;
    max-height: 342px;
    margin-bottom: 24px;
    @media (min-width: 990px) {
      max-height: 600px;
    }
  }
  ul {
    margin-bottom: 24px;
    li {
      position: relative;
      display: flex;
      align-items: center;
      gap: 8px;
      padding-left: 15px;
      @media (min-width: 990px) {
        position: absolute;
        text-align: center;
        color: #2C2C2C;
        font-size: 1rem;
        max-width: 180px;
      }
      &::before {
        content: "";
        position: absolute;
        left: 0;
        top: 50%;
        transform: translateY(-50%);
        display: block;
        width: 7px;
        height: 7px;
        border-radius: 50%;
        background-color: #fff;
        @media (min-width: 990px) {
          display: none;
        }
      }
    }
    @media (min-width: 990px) {
      li:first-child {
        top: 65px;
        left: 0;
      }
      li:nth-child(2) {
        bottom: 110px;
        right: 215px;
      }
      li:last-child {
        bottom: 50%;
        right: 15px;
      }
    }

  }
}
</style>
