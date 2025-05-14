<template>
  <div class="list">
    <Topic
      v-for="topic in topics"
      :key="topic.id"
      :label="topic.label"
      :icon-url="topic.iconUrl"
    />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue';
import Topic from './Topic.vue';

interface TopicItem {
  id: number;
  label: string;
  iconUrl: string;
}

const topics = ref<TopicItem[]>([]);

onMounted(() => {
    topics.value = [
      {
        id: 1,
        label: 'Relationships',
        iconUrl: new URL('@/assets/topics/icon-1.svg', import.meta.url).href,
      },
      {
        id: 2,
        label: 'Skills development',
        iconUrl: new URL('@/assets/topics/icon-2.svg', import.meta.url).href,
      },
      {
        id: 3,
        label: 'Growth mindset',
        iconUrl: new URL('@/assets/topics/icon-3.svg', import.meta.url).href,
      },
      {
        id: 4,
        label: 'Emotional intelligence',
        iconUrl: new URL('@/assets/topics/icon-4.svg', import.meta.url).href,
      },
      {
        id: 5,
        label: 'Self-esteem and confidence',
        iconUrl: new URL('@/assets/topics/icon-5.svg', import.meta.url).href,
      },
    ];
  }
);
</script>

<style scoped>
.list {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 1rem;
  @media (min-width: 990px) {
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
  }
}
</style>

