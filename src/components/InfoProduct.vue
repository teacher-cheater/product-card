<script setup>
import { ref } from "vue";
const title = ref("SONY");
const subtitle = ref("Feel The Music");
const mainTitle = ref("State Of The Sound");
const model = ref("HD 2000");
const description = ref("Wireless Headphones");
const price = ref("$250");
</script>

<template>
  <section class="info-product">
    <div class="info-product__titles">
      <h1 class="info-product__title">{{ title }}</h1>
      <p class="info-product__subtitle">{{ subtitle }}</p>
    </div>
    <div class="info-product__main-text text-main">
      <h3 class="text-main__title">{{ mainTitle }}</h3>
      <p class="text-main__subtitle">{{ model }}</p>
      <p class="text-main__desc">{{ description }}</p>
      <p class="text-main__price">{{ price }}</p>
    </div>
    <div class="info-product__aside-line"></div>
    <button class="info-product__btn-video">
      Watch Video <img src="../assets/images/arrow.svg" alt="arrow next" />
    </button>
  </section>
</template>

<style lang="scss" scoped>
@use "../assets/styles/variables" as *;
.info-product {
  background: $overlay-color;
  padding: 54px 52px 239px;
  max-width: 700px;
  width: 100%;
  border-radius: 0 14px 14px 14px;
  border-right: 15px solid $primary-color;
  border-bottom: 15px solid $primary-color;
  position: relative;
  @media (max-width: 767.98px) {
    max-width: 100%;
    border-radius: 8px;
    padding: 30px 30px 90px;
    border-right: none;
  }
  @media (max-width: 543.98px) {
    padding: 30px;
  }
  &__titles {
    margin-bottom: 131px;
    @media (max-width: 767.98px) {
      margin-bottom: 30px;
    }
  }

  &__title {
    color: rgb(255, 255, 255);
    font-size: 30px;
    font-weight: bold;
    line-height: 1;
  }

  &__subtitle {
    color: rgb(255, 255, 255);
    font-family: Lato;
    font-size: 24px;
    font-weight: 500;
    line-height: 30px;
    text-align: left;
  }

  &__aside-line {
    border-radius: 20px;
    background: rgb(196, 196, 196);
    width: 8px;
    height: 140px;
    position: absolute;
    top: 50%;
    left: 52px;
    transform: translateY(-50%);
    @media (max-width: 767.98px) {
      width: 0;
      height: 0;
    }
  }

  &__aside-line::after {
    content: "";
    position: absolute;
    bottom: 0;
    border-radius: 20px;
    background: $color;
    width: 8px;
    height: 80px;
    @media (max-width: 767.98px) {
      width: 0;
      height: 0;
    }
  }

  &__btn-video {
    font-size: 20px;
    font-weight: 500;
    line-height: 1.2;
    position: absolute;
    bottom: -38px;
    right: 50px;
    border-radius: 10px;
    background: $color;
    padding: 19px 37px;
    display: flex;
    align-items: center;
    color: rgb(0, 0, 0);
    font-family: Lato;
    gap: 14px;
    cursor: pointer;
    @media (max-width: 767.98px) {
      position: static;
      padding: 14px 34px;
    }
  }

  &__btn-video img,
  .submit-btn img {
    background: rgb(255, 255, 255);
    border-radius: 50%;
    padding: 8px 7px;
    transition: all 0.3s ease-in-out 0s;
  }

  &__btn-video:hover img,
  .submit-btn:hover img {
    transform: translateX(5px);
  }
}

.text-main {
  max-width: 476px;
  margin-left: 87px;
  @media (max-width: 767.98px) {
    margin-bottom: 38px;
    max-width: 100%;
    margin-left: 55px;
  }

  &__title {
    max-width: 268px;
    color: rgb(255, 255, 255);
    font-size: 48px;
    font-weight: 600;
    line-height: 1.46;
    margin-bottom: 31px;
    @media (max-width: 767.98px) {
      max-width: 100%;
      font-size: 32px;
      line-height: 1;
    }
  }

  &__subtitle {
    color: $color;
    font-size: 48px;
    font-weight: 500;
    line-height: 1.5;
    margin-bottom: 24px;
    @media (max-width: 767.98px) {
      font-size: 32px;
      line-height: 1;
    }
  }

  &__desc {
    color: rgb(255, 255, 255);
    font-size: 36px;
    font-weight: 400;
    line-height: 1.5;
    margin-bottom: 46px;
    @media (max-width: 767.98px) {
      font-size: 20px;
      line-height: 1;
    }
  }

  &__price {
    color: rgb(255, 255, 255);
    font-family: Lato;
    font-style: italic;
    font-size: 30px;
    font-weight: 400;
    line-height: 1.13;
  }
}
</style>
