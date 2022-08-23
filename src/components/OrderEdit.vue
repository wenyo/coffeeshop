<template>
  <div class="item">
    <div class="idx">#001</div>
    <div class="content">
      <div class="row">
        <div class="row-title">order</div>
        <input class="row-answer input-style" type="text" name="" id="" value="coffeecoffeecoffeecoffeecoffee" />
      </div>
      <div class="row">
        <div class="row-title">size</div>
        <select class="row-answer input-style" name="" id="" value="M">
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
      <button>cancel</button>
    </div>
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
}

.input-style {
  border-bottom: 1px solid $color-dark-300;
}
</style>
