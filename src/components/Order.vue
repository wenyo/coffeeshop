<script setup>
import { defineProps } from "vue";

const props = defineProps({
  order: Object,
  id: Number,
  deleteOrder: Function,
});
</script>

<template>
  <div class="card">
    <div class="title">
      <div class="idx">#{{ id + 1 }}</div>
      <img class="icon icon-close" @click="deleteOrder(id)" src="../assets/icon/xmark-solid.svg" alt="" />
    </div>
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

    <div class="content-bottom">
      <div class="edit">edit</div>
      <div class="time">{{ order.time }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  position: relative;
  transition: all 0.3s;

  &:hover {
    box-shadow: 2px 2px 4px $color-dark-300;

    .icon-close {
      display: inline;
      opacity: 0.8;
    }

    .edit {
      display: inline-block;
    }
  }
}

.title {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
}

.icon-close {
  display: none;
  box-shadow: 0 0 4px $color-dark-400;
  border: 1px solid $color-dark-900;
  padding: 2px;
  cursor: pointer;
  border-radius: 99px;
}

.idx {
  color: $color-primary-300;
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

.content-bottom {
  font-size: 12px;
  display: flex;
  justify-content: space-between;
}

.note,
.time {
  color: $color-dark-400;
}

.note {
  font-size: 12px;
  border-top: 1px solid $color-dark-300;
  padding-top: 10px;
  margin-top: 10px;
  width: 100%;
  height: 30%;
  min-height: 50px;
}

.time {
  text-align: right;
}
</style>
