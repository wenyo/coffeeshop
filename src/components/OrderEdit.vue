<script setup>
import { defineProps, ref } from "vue";
import { SIZE } from "../util/Enum";

const props = defineProps({
  id: Number,
  close: Function,
  order: Object,
  deleteOrder: Function,
  saveOrder: Function,
});

let name = ref(props.order?.name);
let size = ref(props.order?.size ?? "");
let price = ref(props.order?.price);
let note = ref(props.order?.note);

const dateGet = () => {
  const date = new Date();
  let now = `${date.getFullYear()}/${date.getMonth() + 1}/${date.getDate()} ${date.getHours()}:${date.getMinutes()}`;
  return now;
};

function submit() {
  const orderEdit = {
    name: name.value,
    size: size.value,
    price: price.value,
    note: note.value,
    time: dateGet(),
  };

  props.saveOrder(props.id, orderEdit);
}
</script>

<template>
  <div class="order-edit" @click.self="close">
    <div class="card">
      <div class="icon-close" @click="close">
        <img class="icon" src="../assets/icon/xmark-solid.svg" alt="" />
      </div>
      <div class="idx">#{{ id + 1 }}</div>
      <div class="content">
        <div class="row">
          <div class="row-title">order</div>
          <input class="row-answer input-style" type="text" name="" id="" v-model="name" />
        </div>
        <div class="row">
          <div class="row-title">size</div>
          <select class="row-answer input-style" name="" id="" v-model="size">
            <option value="" selected>-</option>
            <option v-for="(size, key) in SIZE" :value="size" :key="key">{{ size }}</option>
          </select>
        </div>
        <div class="row">
          <div class="row-title">price</div>
          <input class="row-answer input-style" type="text" name="" id="" v-model="price" />
        </div>
      </div>
      <div class="note">note</div>
      <textarea class="note-answer" name="" id="" cols="30" rows="2" v-model="note"></textarea>
      <div class="btn-group">
        <button class="btn-secondary hover" @click="submit" :disabled="!name || !price">ok</button>
        <button class="btn-thread hover" v-if="Object.keys(order).length > 0" @click="deleteOrder(id)">dele</button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.order-edit {
  z-index: 10;
  background-color: #{$color-dark-400}#{55};
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.icon-close {
  position: absolute;
  right: 10px;
  top: 10px;
  cursor: pointer;
  opacity: 0.3;

  &:hover {
    opacity: 1;
  }
}

.card {
  padding: 20px;
  position: relative;
  width: 40%;
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
  width: 50%;
  text-align: right;
  word-break: break-all;
}

select.row-answer {
  text-align: center;
}

.note-answer {
  border: 1px solid $color-dark-300;
  width: 100%;
  padding: 3px;
}

.input-style {
  border-bottom: 1px solid $color-dark-300;
}

.btn-group {
  display: flex;
  justify-content: center;
  margin-top: 10px;

  .btn-secondary {
    margin-right: 10px;
  }
}
</style>
