<template>
  <div class="kits">
    <div class="container kits-container">
      <h2 class="title">
        What's included in our educational kits?
      </h2>

      <div class="content-block">
        <div class="list">
          <Kit
            v-for="topic in kits"
            :key="topic.id"
            :label="topic.label"
            :icon-url="topic.iconUrl"
          />
        </div>
        <div class="image">
          <img src="../../assets/kits/img.png" alt="book">
        </div>
      </div>
      <Button
        variant="text-dark"
        size="large"
      >
        Show all kits
        <svg width="18" height="12" viewBox="0 0 18 12" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M9.14147 0.589897C8.90748 0.716135 8.7616 0.956179 8.7616 1.21726V5.28271H0.734294C0.328964 5.28271 0 5.60404 0 5.99997C0 6.3959 0.328964 6.71724 0.734294 6.71724H8.7616V10.7827C8.7616 11.0447 8.90748 11.2848 9.14147 11.4101C9.37547 11.5372 9.66135 11.5286 9.88752 11.39L17.6573 6.60726C17.8708 6.47528 18 6.24671 18 5.99997C18 5.75324 17.8708 5.52467 17.6573 5.39269L9.88752 0.60998C9.76807 0.537298 9.63198 0.5 9.49589 0.5C9.37449 0.5 9.25211 0.530603 9.14147 0.589897Z" fill="#2C2C2C"/>
        </svg>
      </Button>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import Kit from '@/components/Kits/Items/Kit.vue'
import Button from '@/components/Button/Button.vue'

interface KitItem {
  id: number;
  label: string;
  iconUrl: string;
}

const kits = ref<KitItem[]>([]);

onMounted(() => {
    kits.value = [
      {
        id: 1,
        label: 'Presentations for classroom demonstrations',
        iconUrl: new URL('@/assets/kits/1.svg', import.meta.url).href,
      },
      {
        id: 2,
        label: 'Instructional guides for educators',
        iconUrl: new URL('@/assets/kits/2.svg', import.meta.url).href,
      },
      {
        id: 3,
        label: 'Printable handouts for in-class activities',
        iconUrl: new URL('@/assets/kits/3.svg', import.meta.url).href,
      },
      {
        id: 4,
        label: 'Handouts for homework and self-reflection',
        iconUrl: new URL('@/assets/kits/4.svg', import.meta.url).href,
      },
      {
        id: 5,
        label: 'Recommended books and video resources for further study',
        iconUrl: new URL('@/assets/kits/5.svg', import.meta.url).href,
      },
    ];
  }
);
</script>

<style scoped>
.kits {
  background-color: #E8E8ED;
}
.kits-container {
  padding: 3rem 1rem;
}
.title {
  margin-bottom: 24px;
  font-weight: 700;
  font-size: 28px;
  line-height: 120%;
  text-align: center;
  text-transform: uppercase;
  @media (min-width: 990px) {
    font-size: 40px;
  }
}

.content-block {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 24px;
  @media (min-width: 990px) {
    flex-direction: row;
  }
}

.list {
  display: flex;
  flex-direction: column;
  width: 100%;
  gap: 1rem;
  @media (min-width: 990px) {
    max-width: 584px;
  }
}

.image {
  img {
    width: 100%;
    @media (min-width: 990px) {
      width: 584px;
    }
  }
}
</style>
