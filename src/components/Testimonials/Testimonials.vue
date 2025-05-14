<script setup lang="ts">
interface Testimonial {
  id: number;
  review: string;
  sign: string;
}

const testimonials: Testimonial[] = [
  {
    id: 1,
    review: "I find these materials incredibly useful for my 7th-grade classroom. They provide clear, age-appropriate activities and explanations that engage students in discussions about their emotions, including mood swings, during classroom discussions. The resources are easy to integrate into my lessons, and I've already noticed a positive shift in my students' self-awareness. I highly recommend them to any educator looking to enhance their SEL instruction.",
    sign: "Jennifer Carter, Private School Teacher"
  },
  {
    id: 2,
    review: "This kit for teachers is an exceptional resource. The presentation and instructions are well-structured and easy to follow, making it straightforward to deliver engaging lessons. The handouts are practical and provide students with valuable tools for real-life situations.",
    sign: "Michael Thompson, School Counselor"
  },
  {
    id: 3,
    review: "“What I appreciate most is that the materials don’t just focus on solving problems, but also on building stronger connections with other students, parents, and the community itself. The illustrations are also helpful and make a lot more sense compared to a textbook.”",
    sign: "Irene, Homeschooling Parent"
  }
];
</script>

<template>
  <div class="container testimonials-container">
    <h2 class="title">
      Testimonials
    </h2>
    <div class="testimonials-cards">
      <div
        class="testimonial-card"
        v-for="testimonial in testimonials"
        :key="testimonial.id"
      >
        <p class="review">
          {{ testimonial.review }}
        </p>
        <p class="sign">
          {{ testimonial.sign }}
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.testimonials-container {
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
.testimonials-cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 16px;
  @media (min-width: 990px) {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto auto;
    gap: 20px;
  }
}
.testimonial-card {
  padding: 24px 16px;
  background-color: #E8E8ED;
  border-radius: 20px;
  font-weight: 400;
  font-size: 16px;
  line-height: 140%;
  @media (min-width: 990px) {
    padding: 40px
  }
}
.testimonial-card:last-child {
  background-color: #3E468F;
  color: #FFFFFF;
  @media (min-width: 990px) {
    grid-column: 1 / 3;
  }
}
.review {
  margin-bottom: 8px;
}
.sign {
  opacity: .6;
}
</style>
