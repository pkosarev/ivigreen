<script setup lang="ts">

import TopicList from '@/components/Topics/TopicList/TopicList.vue'
</script>

<template>
<div class="container topics-container">
  <h2 class="title">
    The most in-demand topics
  </h2>
  <TopicList />
</div>
</template>

<style scoped>
.topics-container {
  padding: 48px 16px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
  @media (min-width: 990px) {
    gap: 32px;
  }
}
.title {
  font-weight: 700;
  font-size: 28px;
  line-height: 120%;
  text-align: center;
  text-transform: uppercase;
  @media (min-width: 990px) {
    font-size: 40px;
  }
}
.topics-items {
  display: flex;
  flex-direction: column;
  width: 100%;
  @media (max-width: 990px) {
    flex-direction: row;
    flex-wrap: wrap;
  }
}
.topics-items__item {
  font-weight: 500;
  font-size: 20px;
  line-height: 120%;
  color: #3E468F;
  width: 100%;
  padding: 23px 16px;
  border: 1px #3E468F solid;
  border-radius: 100px;
  display: flex;
}
</style>
