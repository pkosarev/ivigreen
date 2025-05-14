<template>
  <div class="navigation">
      <Menu />
  </div>
</template>

<script setup lang="ts">
import Menu from '@/components/Navigation/Menu/Menu.vue'
</script>

<style scoped>
.navigation {
  max-width: 1200px;
  margin: 0 auto;
  padding: 4px 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  @media (min-width: 768px) {
    padding: 1rem 1rem;
  }
}
</style>
