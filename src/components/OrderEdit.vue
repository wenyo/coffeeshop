<template>
  <div class="order-edit">
    <div class="card">
      <img class="icon icon-close" src="../assets/icon/xmark-solid.svg" alt="" />
      <div class="idx">#001</div>
      <div class="content">
        <div class="row">
          <div class="row-title">order</div>
          <input class="row-answer input-style" type="text" name="" id="" value="coffeecoffeecoffeecoffeecoffee" />
        </div>
        <div class="row">
          <div class="row-title">size</div>
          <select class="row-answer input-style" name="" id="">
            <option value="">-</option>
            <option value="S">S</option>
            <option value="M">M</option>
            <option value="L">L</option>
          </select>
        </div>
        <div class="row">
          <div class="row-title">price</div>
          <input class="row-answer input-style" type="text" name="" id="" value="60" />
        </div>
      </div>
      <div class="note">note</div>
      <textarea class="note-answer" name="" id="" cols="30" rows="2"></textarea>
      <div class="btn-group">
        <button>ok</button>
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

  &:hover{
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
</style>
