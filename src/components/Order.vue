<script setup>
import { defineProps } from "vue";

const props = defineProps({
  order: Object,
  id: Number,
  deleteOrder: Function,
  orderEdit: Function,
});
</script>

<template>
  <div class="card">
    <div class="title">
      <div class="idx">#{{ id + 1 }}</div>
    </div>

    <div class="icon-close" @click="deleteOrder(id)">
      <img class="icon" src="../assets/icon/xmark-solid.svg" alt="" />
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
      <div class="time">{{ order.time }}</div>
      <button class="edit btn-primary hover" @click="orderEdit(id)">edit</button>
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
    }

    .edit {
      display: inline-block;
    }
  }
}

.edit {
  display: none;
  @media (max-width: 768px) {
    display: inline-block;
  }
}

.title {
  margin-bottom: 20px;
  display: flex;
  justify-content: space-between;
}

.icon-close {
  display: none;
  opacity: 0.3;
  position: absolute;
  top: 10px;
  right: 10px;
  cursor: pointer;
  border-radius: 99px;
  transition: all 0.3s;

  &::after {
    content: "";
    position: absolute;
    top: -2px;
    right: -2px;
    bottom: -2px;
    left: -2px;
  }

  &:hover {
    opacity: 1;
  }

  @media (max-width: 768px) {
    display: inline;
  }
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
  flex-direction: row-reverse;
}

.note,
.time {
  font-size: 12px;
  color: $color-dark-400;
}

.note {
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
