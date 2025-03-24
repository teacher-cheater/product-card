<script>
export default {};
</script>

<template>
  <div class="product-characteristic">
    <table class="product-characteristic__table">
      <tbody>
        <tr>
          <td>Модель</td>
          <td>XYZ-123</td>
        </tr>
        <tr>
          <td>Тип</td>
          <td>Беспроводные</td>
        </tr>
        <tr>
          <td>Автономность</td>
          <td>20 часов</td>
        </tr>
        <tr>
          <td>Вес, г</td>
          <td>386</td>
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
