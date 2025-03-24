<script setup>
import { defineEmits } from "vue";
const props = defineProps({
  activeTab: String,
});
const emit = defineEmits(["open", "changeTab"]);
</script>

<template>
  <div class="header-card">
    <button
      class="header-card__btn tab-btn"
      :class="{ active: activeTab === 'product' }"
      @click="emit('changeTab', 'product')"
    >
      product
    </button>
    <button
      class="header-card__btn tab-btn"
      :class="{ active: activeTab === 'description' }"
      @click="emit('changeTab', 'description')"
    >
      description
    </button>
    <button
      class="header-card__btn tab-btn"
      :class="{ active: activeTab === 'characteristics' }"
      @click="emit('changeTab', 'characteristics')"
    >
      characteristics
    </button>
    <button @click="emit('open')" class="header-card__btn order-btn">
      ORDER NOW
    </button>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles/variables" as *;
.header-card {
  display: grid;
  grid-template-columns: repeat(4, 169px);
  gap: 20px;
  padding: 51px 30px 65px 30px;

  &__btn {
    padding: 19px 42px;
    border: none;
    outline: none;
    background-color: $primary-color;
    text-transform: uppercase;
    color: rgb(0, 0, 0);
    font-family: Lato;
    font-size: 20px;
    font-weight: 500;
    line-height: 1.2;
    border-radius: 40px;
    cursor: pointer;
    transition: all 0.4s ease-in-out 0s;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }

  &__btn:hover {
    background-color: $color;
    color: rgb(255, 255, 255);
  }
}

.tab-btn {
  padding: 10px 15px;
  cursor: pointer;
  border: none;
}

.tab-btn.active {
  background: $secondary-color;
  color: rgb(255, 255, 255);
}
</style>
