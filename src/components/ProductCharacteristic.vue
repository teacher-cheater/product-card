<script setup>
import { ref } from "vue";
const productModel = ref("XYZ-123");
const productType = ref("Беспроводные");
const productAutonomy = ref("20 часов");
const productWeight = ref("386");
</script>

<template>
  <div class="product-characteristic">
    <table class="product-characteristic__table">
      <tbody>
        <tr>
          <td>Модель</td>
          <td>{{ productModel }}</td>
        </tr>
        <tr>
          <td>Тип</td>
          <td>{{ productType }}</td>
        </tr>
        <tr>
          <td>Автономность</td>
          <td>{{ productAutonomy }}</td>
        </tr>
        <tr>
          <td>Вес, г</td>
          <td>{{ productWeight }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style lang="scss" scoped>
@use "../assets/styles/variables" as *;
.product-characteristic {
  margin: 0 auto 45px;
  flex: auto;

  &__table {
    background: white;
    padding: 20px;
    text-align: center;
    width: 600px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
    position: relative;
    border: 10px solid $color;
    border-radius: 30px;
    border-collapse: collapse;
    @media (max-width: 767.98px) {
      width: 100%;
    }
  }

  &__table td {
    padding: 12px;
    border-bottom: 2px solid $color;
    font-size: 18px;
    font-weight: bold;
    color: #333;
  }

  &__table tr:last-child td {
    border-bottom: none;
  }
}
</style>
