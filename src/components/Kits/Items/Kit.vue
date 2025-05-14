<script setup lang="ts">
defineProps<{
  iconUrl: string;
  label: string;
}>();
</script>

<template>
  <div class="kit">
    <div class="icon">
      <img :src="iconUrl" alt="icon" />
    </div>
    <span class="text">{{ label }}</span>
  </div>
</template>

<style scoped>
.kit {
  display: flex;
  align-items: center;
  padding: 8px;
  background-color: #FFFFFF;
  border-radius: 20px;
  width: 100%;
  cursor: pointer;
  @media (min-width: 990px) {
    height: 116px;
  }
}

.icon {
  width: 70px;
  height: 70px;
  margin-right: 1rem;
}

.icon img {
  width: 70px;
  height: 70px;
}

.text {
  color: #2C2C2C;
  font-size: 16px;
  font-weight: 500;
  line-height: 150%;
}
</style>
