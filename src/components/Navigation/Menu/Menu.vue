<template>
  <nav class="menu">
    <ul>
      <li>
        <Logo />
      </li>
      <li class="nav-item-list">
        <a href="#" class="nav-item">Products</a>
      </li>
      <li class="nav-item-list">
        <a href="#" class="nav-item">About Ivi Green</a>
      </li>
      <li class="nav-item-list">
        <a href="#" class="nav-item">FAQ</a>
      </li>
      <li class="nav-item-list">
        <a href="#" class="nav-item">For educators</a>
      </li>
      <li class="nav-item-list">
        <a href="#" class="nav-item">Blog</a>
      </li>
      <li>
        <div class="menu-container-right">
          <div class="cart-wrapper">
            <Cart />
            <div class="cart-counter">0</div>
          </div>
          <Burger v-if="isScreenLarge"/>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import Logo from '@/components/icons/Logo.vue'
import Cart from '@/components/icons/Cart.vue'
import Burger from '@/components/icons/Burger.vue'

import { ref, onMounted, onBeforeUnmount } from 'vue';

const isScreenLarge = ref<boolean>(false);

const updateScreenSize = (): void => {
  isScreenLarge.value = window.innerWidth < 768;
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
 .menu {
   display: flex;
   width: 100%;
   ul {
     display: flex;
     justify-content: space-between;
     align-items: center;
     width: 100%;
     .nav-item-list {
       display: none;
       @media (min-width: 768px) {
         display: flex;
         justify-content: space-between;
         align-items: center;
       }
       .nav-item {
         font-weight: 500;
         font-size: 20px;
         line-height: 150%;
         color: #2C2C2C;
       }
     }
   }
 }
 .menu-container-right {
   display: flex;
   align-items: center;
   gap: 30px;
 }
 .cart-wrapper {
   display: flex;
   width: fit-content;
   height: fit-content;
   cursor: pointer;
   position: relative;
 }
 .cart-counter {
   position: absolute;
   top: 0;
   right: 0;
   transform: translate(40%, -40%);
   border-radius: 24px;
   background-color: #32CD7A;
   display: inline-flex;
   padding: 0 8px;
   justify-content: center;
   align-items: center;
   color: #fff;
   text-align: center;
   font-size: 16px;
   font-weight: 500;
   line-height: 160%;
 }
</style>
