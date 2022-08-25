<script setup>
import { ref } from "vue";
import Order from "./components/Order.vue";
import OrderEdit from "./components/OrderEdit.vue";
import SAMPLE_DATA from "./assets/json/sample.json";

let orderList = ref(SAMPLE_DATA.order_list);

function initialDataGet() {
  return SAMPLE_DATA;
}

function deleteOrder(id) {
  orderList.value.splice(id, 1);
}
</script>

<template>
  <main>
    <h1 class="title">Coffee Shop</h1>
    <!-- <OrderEdit /> -->
    <div class="order-list">
      <Order v-for="(order, key) in orderList" :delete-order="deleteOrder" :order="order" :id="key" :key="key" />
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
  grid-template-columns: repeat(3, 1fr);
  grid-column-gap: 20px;
  grid-row-gap: 20px;
  width: 100%;
}
</style>
