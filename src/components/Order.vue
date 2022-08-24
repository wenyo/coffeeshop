<script setup>
import { defineProps } from "vue";

const props = defineProps({
  order: Object,
  id: String,
});
</script>

<template>
  <div class="item">
    <div class="idx">#{{ id }}</div>
    <div class="content">
      <div class="row">
        <div class="row-title">order</div>
        <div class="row-answer">{{ order.name }}</div>
      </div>
      <div class="row">
        <div class="row-title">size</div>
        <div class="row-answer">{{ order.size }}</div>
      </div>
      <div class="row">
        <div class="row-title">price</div>
        <div class="row-answer">{{ order.price }}</div>
      </div>
    </div>
    <div class="note">{{ order.note }}</div>
    <div class="time">{{ order.time }}</div>
  </div>
</template>

<style lang="scss" scoped>
.item {
  padding: 10px;
  box-shadow: 0 0 4px $color-dark-300;
}

.row {
  margin: 4px 0;
  display: flex;
  justify-content: space-between;
}

.row-title {
  flex-shrink: 0;
}

.row-answer {
  margin-left: 10px;
  text-align: right;
  word-break: break-all;
}
</style>
