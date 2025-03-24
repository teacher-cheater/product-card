<script setup>
import { ref } from "vue";

const productDescription = ref(
  "Это сочетание технологий и превосходного звучания, которое предлагает пользователям отличное качество звука. Эти наушники создают полное погружение в звук благодаря глубоким басам, чётким средним частотам, кристально чистым верхам."
);
</script>

<template>
  <div class="product-desc">
    <p class="product-desc__text">{{ productDescription }}</p>
  </div>
</template>

<style lang="scss" scoped>
.product-desc {
  flex: auto;
  &__text {
    font-size: 20px;
    font-weight: 500;
    line-height: 1.2;
    color: #000;
    padding: 10px 64px 10px 51px;
    @media (max-width: 767.98px) {
      padding: 12px;
    }
  }
}
</style>
