<script setup>
import ProductCharacteristic from "./ProductCharacteristic.vue";
import ProductDescription from "./ProductDescription.vue";
import HeaderCard from "./HeaderCard.vue";
import OrderCard from "./OrderCard.vue";
import SliderProduct from "./SliderProduct.vue";
import { ref } from "vue";

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
  <main class="main">
    <section class="sony">
      <div class="sony__titles">
        <h1 class="sony__title">SONY</h1>
        <p class="sony__subtitle">Feel The Music</p>
      </div>
      <div class="sony__main-text text-main">
        <h3 class="text-main__title">State Of The Sound</h3>
        <p class="text-main__subtitle">HD 2000</p>
        <p class="text-main__desc">Wireless Headphones</p>
        <p class="text-main__price">$250</p>
      </div>
      <div class="sony__aside-line"></div>
      <button class="sony__btn-video">
        Watch Video <img src="../assets/arrow.svg" alt="arrow next" />
      </button>
    </section>
    <section class="main__wrapper">
      <HeaderCard
        @open="openModal"
        :activeTab="activeTab"
        @changeTab="setActiveTab"
      />
      <div class="main__info">
        <h3 class="main__subtitle">02</h3>
        <h2 class="main__title">BASS BOOSTED HEADPHONES</h2>
      </div>

      <ProductDescription v-if="activeTab === 'description'" />

      <ProductCharacteristic v-if="activeTab === 'characteristics'" />

      <OrderCard :visible="dialogVisible" @close="closeModal" />

      <SliderProduct v-if="activeTab === 'product'" />

      <div class="main__text">
        <p class="main__description">WIRELESS HEADPHONES</p>
        <a href="#" class="main__link">WINDOWS COMPATIBLE</a>
      </div>
    </section>
  </main>
</template>

<style lang="scss" scoped>

</style>
