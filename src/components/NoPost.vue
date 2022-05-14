<template>
  <div class="noPost">
    <div class="noPost__header">
      <span class="item red"></span>
      <span class="item yellow"></span>
      <span class="item green"></span>
    </div>
    <div class="noPost__body">
      <p>目前尚無動態，新增一則貼文吧！</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.noPost {
  width: 100%;
  height: 132px;
  margin-top: 16px;
  box-shadow: 0px 3px 0px #000400;
  border: 2px solid #000400;
  border-radius: 8px;
  background-color: #fff;
  &__header {
    height: 40px;
    border-bottom: 2px solid #000400;
    display: flex;
    align-items: center;
    padding-left: 12px;
    .item {
      display: block;
      width: 9px;
      height: 9px;
      border-radius: 50%;
      margin-right: 6px;
      border: 1px solid #707070;
      &.red {
        background-color: #DE4B63;
      }
      &.yellow {
        background-color: #FAA722;
      }
      &.green {
        background-color: #83C51D;
      }
    }
  }
  &__body {
    display: flex;
    justify-content: center;
    padding: 30px 0;
    p {
      font-size: 16px;
      line-height: 24px;
      color: #9B9893;
      margin-bottom: 0;
    }
  }
}
</style>
