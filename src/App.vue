<script setup>
import Order from "./components/Order.vue";
import OrderEdit from "./components/OrderEdit.vue";

</script>

<template>
  <main>
    <h1 class="title">Coffee Shop</h1>
    <div class="order-list">
      <Order />
      <Order />
      <Order />
      <Order />
      <Order />
      <Order />
      <Order />
      <Order />
      <OrderEdit />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: $color-dark-200;
  color: $color-dark-900;
  padding: 40px 20px;
}

.title {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 20px;
}

.order-list {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-column-gap: 10px;
  grid-row-gap: 10px;
  width: 100%;
}
</style>
