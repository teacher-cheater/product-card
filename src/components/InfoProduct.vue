<script setup></script>

<template>
  <section class="info-product">
    <div class="info-product__titles">
      <h1 class="info-product__title">info-product</h1>
      <p class="info-product__subtitle">Feel The Music</p>
    </div>
    <div class="info-product__main-text text-main">
      <h3 class="text-main__title">State Of The Sound</h3>
      <p class="text-main__subtitle">HD 2000</p>
      <p class="text-main__desc">Wireless Headphones</p>
      <p class="text-main__price">$250</p>
    </div>
    <div class="info-product__aside-line"></div>
    <button class="info-product__btn-video">
      Watch Video <img src="../assets/arrow.svg" alt="arrow next" />
    </button>
  </section>
</template>

<style lang="scss" scoped>
.info-product {
  background: rgb(40, 40, 40);
  padding: 54px 52px 239px;
  max-width: 700px;
  width: 100%;
  border-radius: 0 14px 14px 14px;
  border-right: 15px solid rgb(192, 187, 255);
  border-bottom: 15px solid rgb(192, 187, 255);
  position: relative;

  &__titles {
    margin-bottom: 131px;
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
  }

  &__aside-line::after {
    content: "";
    position: absolute;
    bottom: 0;
    border-radius: 20px;
    background: rgb(146, 136, 255);
    width: 8px;
    height: 80px;
  }

  &__btn-video,
  .submit-btn {
    font-size: 20px;
    font-weight: 500;
    line-height: 1.2;
    position: absolute;
    bottom: -38px;
    right: 50px;
    border-radius: 10px;
    background: rgb(146, 136, 255);
    padding: 19px 37px;
    display: flex;
    align-items: center;
    color: rgb(0, 0, 0);
    font-family: Lato;
    gap: 14px;
    cursor: pointer;
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

  &__title {
    max-width: 268px;
    color: rgb(255, 255, 255);
    font-size: 48px;
    font-weight: 600;
    line-height: 1.46;
    margin-bottom: 31px;
  }

  &__subtitle {
    color: rgb(146, 136, 255);
    font-size: 48px;
    font-weight: 500;
    line-height: 1.5;
    margin-bottom: 24px;
  }

  &__desc {
    color: rgb(255, 255, 255);
    font-size: 36px;
    font-weight: 400;
    line-height: 1.5;
    margin-bottom: 46px;
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
