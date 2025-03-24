<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  visible: Boolean,
});

const emit = defineEmits(["close"]);
</script>

<template>
  <div class="modal" v-if="visible">
    <div class="modal-content">
      <span class="close-btn" @click="emit('close')">&times;</span>
      <h2>Order now</h2>
      <input type="text" placeholder="Name" id="name" />
      <input type="tel" placeholder="Phone number" id="phone" />
      <button class="submit-btn">
        Send <img src="../assets/images/arrow.svg" alt="arrow next" />
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles/variables" as *;
.order-form {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  transition: opacity 0.3s, visibility 0.3s;
  z-index: 5;
}

.modal-content {
  background: white;
  padding: 20px;
  text-align: center;
  width: 400px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
  position: relative;

  border: 10px solid $color;
  border-radius: 30px;
  & h2 {
    font-family: Lato;
    font-size: 24px;
    font-weight: 700;
    line-height: 1.125;
  }
}

.close-btn {
  position: absolute;
  top: 10px;
  right: 15px;
  font-size: 20px;
  cursor: pointer;
}

.modal input {
  display: block;
  width: 100%;
  margin: 10px 0;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.submit-btn {
  font-size: 20px;
  font-weight: 500;
  line-height: 1.2;
  border-radius: 10px;
  background: $color;
  display: flex;
  align-items: center;
  color: rgb(0, 0, 0);
  font-family: Lato;
  gap: 14px;
  cursor: pointer;
  position: static;
  padding: 12px 22px;
  text-transform: uppercase;
  justify-content: flex-end;
  & img {
    width: 30px;
    height: 30px;
    background: rgb(255, 255, 255);
    border-radius: 50%;
    padding: 8px 7px;
    transition: all 0.3s ease-in-out 0s;
  }
  &:hover {
    & img {
      background: rgb(255, 255, 255);
      border-radius: 50%;
      padding: 8px 7px;
      transition: all 0.3s ease-in-out 0s;
    }
    &:hover img {
      transform: translateX(5px);
    }
  }
}

</style>
