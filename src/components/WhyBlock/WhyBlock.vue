<template>
  <div class="container why-container">
    <h2 class="title">
      Why Ivi Green?
    </h2>
    <div class="why-top-block">
      <div
        class="why-item"
        v-for="(item, index) in whyItems"
        :key="index"
      >
        <h3 class="why-item__title">
          {{ item.title }}
        </h3>
        <p class="why-item__description">
          {{ item.description }}
        </p>
      </div>
    </div>

    <div class="why-bottom-block">
      <div
        class="bottom-block__item"
        v-for="(item, index) in bottomItems"
        :key="index"
      >
        <h3 class="bottom-block__item--title">
          {{ item.title }}
        </h3>
        <p class="bottom-block__item--description">
          {{ item.description }}
        </p>
      </div>
    </div>

    <Button
      size="adaptive"
    >
      Show all kits
    </Button>
  </div>
</template>

<script setup lang="ts">
import Button from '@/components/Button/Button.vue'

interface WhyItem {
  title: string;
  description: string;
}

const whyItems: WhyItem[] = [
  {
    title: "40 000+",
    description: "products sold all around the world"
  },
  {
    title: "1 000+",
    description: "teachers use Ivi Green products"
  },
  {
    title: "30+",
    description: "countries use our toolkits to effectively teach "
  }
];

const bottomItems: WhyItem[] = [
  {
    title: "The challenges teachers are facing",
    description: "Teachers often face the challenge of spending extensive time searching for quality materials for their classes while students frequently approach them with more and more questions about their emotions, conflicts, self-organization methods, and family or friend relationships. The pandemic has exacerbated social-emotional problems among kids, making SEL one of the priorities for the school curriculum. Now even teachers specializing in subjects like math or language art need to incorporate social-emotional basics into their instructions.",
  },
  {
    title: "Our solution",
    description: "Our toolkits provide teachers with practical, visual, science-based resources to effectively teach social and emotional learning to teens. Designed to enhance emotional intelligence and build resilience, Ivi Green educational toolkits offer structured activities, comprehensive guidelines, and ready-to-use materials that cater to the unique developmental needs of adolescents. Educators can foster a supportive learning environment that promotes emotional well-being and academic success by integrating these tools into their teaching.",
  }
]

</script>

<style scoped>
.why-container {
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
  text-transform: uppercase;
  @media (min-width: 990px) {
    font-size: 40px;
  }
}
.why-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}
.why-top-block,
.why-bottom-block {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 16px;
  @media (min-width: 990px) {
    width: 100%;
    flex-direction: row;
    justify-content: space-between;
  }
}
.why-item__title {
  font-weight: 700;
  font-size: 36px;
  line-height: 110%;
  color: #32CD7A;
  @media (min-width: 990px) {
    font-size: 64px;
  }
}
.why-item__description {
  font-weight: 500;
  font-size: 16px;
  line-height: 150%;
  color: #2C2C2C;
  text-align: center;
  @media (min-width: 990px) {
    font-size: 20px;
    max-width: 284px;
  }
}
.why-bottom-block {
  @media (min-width: 990px) {
    gap: 20px;
    height: 100%;
  }
}
.bottom-block__item {
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding: 24px 16px;
  background-color: #E8E8ED;
  border-radius: 20px;
  @media (min-width: 990px) {
    padding: 40px;
    height: 100%;
  }
}
.bottom-block__item--title {
  font-weight: 500;
  font-size: 20px;
  line-height: 120%;
  max-width: 277px;
  color: #3E468F;
  @media (min-width: 990px) {
    font-size: 28px;
    width: 100%;
  }
  @media (min-width: 1166px) {
    white-space: nowrap;
  }
}

.bottom-block__item--description {
  font-weight: 400;
  font-size: 16px;
  line-height: 140%;
}
</style>
