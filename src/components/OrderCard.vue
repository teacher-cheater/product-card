<script setup>
import { defineProps, defineEmits, ref } from "vue";

const props = defineProps({
  visible: Boolean,
});

const emit = defineEmits(["close"]);

const name = ref("");
const phone = ref("");
const errors = ref({ name: "", phone: "" });

const validateForm = () => {
  errors.value = { name: "", phone: "" };

  if (!name.value.trim()) {
    errors.value.name = "Введите имя!";
  }

  if (!phone.value.trim()) {
    errors.value.phone = "Введите номер телефона!";
  } else if (!/^\+?\d{10,15}$/.test(phone.value)) {
    errors.value.phone = "Введите корректный номер!";
  }

  return !errors.value.name && !errors.value.phone;
};

const submitForm = () => {
  if (!validateForm()) {
    return;
  }
  alert(`Name: ${name.value}, Phone: ${phone.value}`);
  name.value = "";
  phone.value = "";
};

</script>

<template>
  <div class="modal" v-if="visible">
    <div class="modal__container">
      <span class="modal__close-btn" @click="emit('close')">&times;</span>
      <h2>Order now</h2>
      <input type="text" placeholder="Name" v-model="name" />
      <p v-if="errors.name" class="modal__error">{{ errors.name }}</p>
      <input type="tel" placeholder="Phone number" v-model="phone" />
      <p v-if="errors.phone" class="modal__error">{{ errors.phone }}</p>
      <button class="modal__submit-btn" @click="submitForm">
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
  &__container {
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

  &__close-btn {
    position: absolute;
    top: 10px;
    right: 15px;
    font-size: 20px;
    cursor: pointer;
  }

  & input {
    display: block;
    width: 100%;
    margin: 10px 0;
    padding: 8px;
    border: 1px solid $color;
    border-radius: 5px;
  }

  &__error {
    color: red;
    font-size: 14px;
  }

  &__submit-btn {
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
}
</style>
