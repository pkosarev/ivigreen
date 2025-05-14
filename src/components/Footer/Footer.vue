<script setup lang="ts">

import Button from '@/components/Button/Button.vue'
</script>

<template>
  <footer class="container footer">
      <div class="footer-inner">
        <div class="footer-form">
          <h2 class="footer-header">
            Drop your email to receive complimentary printables for your teens
          </h2>
          <div class="footer-input-field">
          <input class="footer-email" type="email" placeholder="Enter your E-mail">
            <Button
              size="large"
            >
              Get for free
            </Button>
          </div>
          <p class="footer-text">
            By giving us your e-mail, you agree to our
            <a href="#" class="footer-text-privacy-policy" target="_blank">privacy policy</a>
          </p>
        </div>
        <div class="footer-info">
          <a class="term-of-use" href="#" target="_blank">Terms of Use</a>
          <a class="email" href="#">hello@ivigreen.com</a>
        </div>
      </div>
  </footer>
</template>

<style scoped>
.footer {
  padding: 48px 16px 24px;
}
.footer-inner {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
}
.footer-form {
  padding: 40px 16px;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  border-radius: 20px;
  color: #fff;
  background: #3e468f;
}
.footer-header {
  font-weight: 500;
  font-size: 20px;
  margin-bottom: 32px;
  line-height: 120%;
  text-align: center;
  @media (min-width: 990px) {
    font-size: 28px;
  }
}
.footer-input-field {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 24px;
  width: 100%;
  height: fit-content;
  margin-bottom: 16px;
  max-width: 771px;
  @media (min-width: 990px) {
    flex-direction: row;
  }
}
.footer-email {
  padding: 14px 16px;
  outline: none;
  width: 100%;
  border-radius: 8px;
  font-size: 18px;
}
.footer-text {
  text-align: center;
  line-height: 160%;
  font-size: 12px;
  @media (min-width: 990px) {
    font-size: 16px;
  }
}
.footer-text-privacy-policy {
  color: #32cd7a;
}
.footer-info {
  display: flex;
  justify-content: space-between;
  width: 100%;
  font-size: 16px;
  color: #3E468F;
  line-height: 160%;
  text-decoration-line: underline;
  @media (min-width: 990px) {
    font-size: 20px;
  }
}
</style>
