<template>
  <div class="topic">
    <div class="icon">
      <img :src="iconUrl" alt="icon" />
    </div>
    <span class="text">{{ label }}</span>
  </div>
</template>

<script lang="ts" setup>
defineProps<{
  iconUrl: string;
  label: string;
}>();
</script>

<style scoped>
.topic {
  display: flex;
  align-items: center;
  padding-right: 1rem;
  border: 1px solid #3f448f;
  border-radius: 100px;
  width: 100%;
  cursor: pointer;
  @media (min-width: 990px) {
    max-width: fit-content;
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
  color: #3f448f;
  font-size: 20px;
  font-weight: 500;
  line-height: 120%;
}
</style>

