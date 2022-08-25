<script setup>
import { ref } from "vue";
import Order from "./components/Order.vue";
import OrderEdit from "./components/OrderEdit.vue";
import SAMPLE_DATA from "./assets/json/sample.json";
import { IDX_EMPTY } from "./util/Enum";

let orderList = ref(SAMPLE_DATA.order_list);
let orderAlert = ref(false);
let orderEditIdx = ref(IDX_EMPTY);

function initialDataGet() {
  return SAMPLE_DATA;
}

function orderDelete(id) {
  orderList.value.splice(id, 1);
}

function orderSave(id, order) {
  orderList.value[id] = order;
}

function orderEdit(id = IDX_EMPTY) {
  orderAlert.value = true;
  orderEditIdx.value = id;
}

function orderAlertClose() {
  orderAlert.value = false;
  orderEditIdx.value = IDX_EMPTY;
}

function orderDeleteFromAlert(id) {
  orderDelete(id);
  orderAlertClose();
}

function orderSaveFromAlert(id, order) {
  orderSave(id, order);
  orderAlertClose();
}
</script>

<template>
  <main>
    <div class="title">
      <h1>Coffee Shop</h1>
      <button class="btn-secondary btn-add" @click="orderEdit()">ADD</button>
    </div>
    <OrderEdit
      v-if="orderAlert"
      :id="orderEditIdx === IDX_EMPTY ? orderList.length : orderEditIdx"
      :order="orderEditIdx === IDX_EMPTY ? {} : orderList[orderEditIdx]"
      :close="orderAlertClose"
      :delete-order="orderDeleteFromAlert"
      :save-order="orderSaveFromAlert"
    />
    <div class="order-list">
      <Order v-for="(order, key) in orderList" :order="order" :id="key" :key="key" :order-edit="orderEdit" :delete-order="orderDelete" />
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
  position: relative;
  width: 100%;
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 20px;
  border-bottom: 1px solid $color-dark-300;
}

.order-list {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 20px;
  width: 100%;
}

.btn-add {
  position: absolute;
  right: 0;
  top: 0;
}
</style>
