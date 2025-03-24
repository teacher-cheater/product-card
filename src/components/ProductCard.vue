<script setup>
import ProductCharacteristic from "./ProductCharacteristic.vue";
import ProductDescription from "./ProductDescription.vue";
import HeaderCard from "./HeaderCard.vue";
import OrderCard from "./OrderCard.vue";
import SliderProduct from "./SliderProduct.vue";
import { ref } from "vue";
import InfoProduct from "./InfoProduct.vue";

const dialogVisible = ref(false);
const activeTab = ref("product");

const setActiveTab = tab => {
  activeTab.value = tab;
};

const openModal = () => {
  dialogVisible.value = true;
};

const closeModal = () => {
  dialogVisible.value = false;
};
</script>

<template>
  <main class="product-card">
    <InfoProduct />
    <section class="product-card__wrapper">
      <HeaderCard
        @open="openModal"
        :activeTab="activeTab"
        @changeTab="setActiveTab"
      />
      <div class="product-card__info">
        <h3 class="product-card__subtitle">02</h3>
        <h2 class="product-card__title">BASS BOOSTED HEADPHONES</h2>
      </div>

      <ProductDescription v-if="activeTab === 'description'" />

      <ProductCharacteristic v-if="activeTab === 'characteristics'" />

      <OrderCard :visible="dialogVisible" @close="closeModal" />

      <SliderProduct v-if="activeTab === 'product'" />

      <div class="product-card__text">
        <p class="product-card__description">WIRELESS HEADPHONES</p>
        <a href="#" class="product-card__link">WINDOWS COMPATIBLE</a>
      </div>
    </section>
  </main>
</template>

<style lang="scss" scoped>
.product-card {
  display: flex;
  width: 1480px;
  margin: 20px auto;
  padding: 0 0 137px 0;
  border: 20px solid rgb(0, 0, 0);
  border-radius: 30px;
  box-shadow: 30px 30px 20px 0px rgba(146, 136, 255, 0.4);
  background: rgb(255, 255, 255);
  &__wrapper {
    width: 100%;
    display: flex;
    flex-direction: column;
  }

  &__info {
    padding: 0px 64px 10px 51px;
  }

  &__subtitle {
    color: rgba(40, 40, 40, 0.8);
    font-family: Lato;
    font-size: 50px;
    font-weight: 400;
    margin-bottom: 12px;
  }

  &__title {
    max-width: 276px;
    color: rgb(59, 45, 222);
    font-family: Lato;
    font-size: 36px;
    font-weight: 400;
    line-height: 1.11;
  }
  &__text {
    text-align: center;
  }

  &__description,
  &__link {
    font-family: Lato;
    font-size: 24px;
    font-weight: 700;
    line-height: 1.125;
  }

  &__link {
    color: rgb(59, 45, 222);
  }
}
</style>
