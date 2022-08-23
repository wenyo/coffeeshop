<template>
  <div class="item">
    <div class="idx">#001</div>
    <div class="content">
      <div class="row">
        <div class="row-title">order</div>
        <div class="row-answer">coffeecoffeecoffeecoffeecoffee</div>
      </div>
      <div class="row">
        <div class="row-title">size</div>
        <div class="row-answer">M</div>
      </div>
      <div class="row">
        <div class="row-title">price</div>
        <div class="row-answer">60</div>
      </div>
    </div>
    <div class="note">note</div>
    <div class="time">2022/08/23 12:17</div>
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

.row-title{
    flex-shrink: 0;
}

.row-answer{
    margin-left: 10px;
    text-align: right;
    word-break: break-all;
}
</style>
