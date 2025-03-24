<script setup>
import { ref, computed } from "vue";
const images = ref([
  new URL("../assets/headphones-1.jpg", import.meta.url).href,
  new URL("../assets/headphones-2.jpg", import.meta.url).href,
  new URL("../assets/headphones-3.jpg", import.meta.url).href,
]);

const activeImage = ref(0);

// const currentImage = computed(() => images.value[activeImage.value]);

const nextSlide = () => {
  activeImage.value = (activeImage.value + 1) % images.value.length;
};

const prevSlide = () => {
  activeImage.value =
    activeImage.value === 0 ? images.value.length - 1 : activeImage.value - 1;
};
</script>

<template>
  <div class="carousel">
    <button class="btn-prev" @click="prevSlide">
      <img src="../assets/arrow-left.svg" alt="prev" />
    </button>
    <button class="btn-next" @click="nextSlide">
      <img src="../assets/arrow-right.svg" alt="next" />
    </button>
    <div class="carousel__wrapper">
      <div
        class="carousel__line"
        :style="{ transform: `translateX(-${activeImage * 100}%)` }"
      >
        <!-- slider images -->
        <img
          v-for="(img, index) in images"
          :src="`${img}`"
          :key="index"
          :class="{ active: index === activeImage }"
          alt="headephone"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.carousel {
  position: relative;
  width: 603px;
  height: 452px;

  margin: 0 auto 45px;
  flex: auto;

  &__wrapper {
    overflow: hidden;
    width: 100%;
    height: 100%;
    overflow: hidden;
  }

  &__line {
    display: flex;
    transition: transform 0.4s ease-in-out;
    & img {
      width: 100%;
      height: auto;
      flex-shrink: 0;
    }
    & img.active {
      position: relative;
      overflow: visible;
      opacity: 1;
      max-width: 603px;
      max-height: 452px;
    }
  }
}

.btn-prev,
.btn-next {
  background: rgb(192, 187, 255);
  padding: 12px 31px;
  position: absolute;
  top: 30%;
  cursor: pointer;
  z-index: 3;
}
.btn-prev img,
.btn-next img {
  transition: transform 0.2s ease-in-out 0s;
}

.btn-prev {
  left: -97px;
  border-radius: 0 30px 30px 0;
}
.btn-prev:hover img {
  transform: translateX(-8px) scale(1.2);
}

.btn-next {
  right: -97px;
  border-radius: 30px 0 0 30px;
}
.btn-next:hover img {
  transform: translateX(8px) scale(1.2);
}
</style>
