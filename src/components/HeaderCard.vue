<script setup>
import { defineEmits } from "vue";
const props = defineProps({
  activeTab: String,
});
const emit = defineEmits(["open", "changeTab"]);
</script>

<template>
  <div class="main__header">
    <button
      class="main__btn tab-btn"
      :class="{ active: activeTab === 'product' }"
      @click="emit('changeTab', 'product')"
    >
      product
    </button>
    <button
      class="main__btn tab-btn"
      :class="{ active: activeTab === 'description' }"
      @click="emit('changeTab', 'description')"
    >
      description
    </button>
    <button
      class="main__btn tab-btn"
      :class="{ active: activeTab === 'characteristics' }"
      @click="emit('changeTab', 'characteristics')"
    >
      characteristics
    </button>
    <button @click="emit('open')" class="main__btn order-btn">ORDER NOW</button>
  </div>
</template>

<style lang="scss" scoped>
  

</style>
