<template>
  <div class="sideBar">
    <div class="postBtn">
      <router-link to="/create">
        張貼動態
      </router-link>
    </div>
    <div class="sideBar__item">
      <span></span>
      <div class="sideBar__item__name">邊緣小杰</div>
    </div>
    <div class="sideBar__item">
      <span></span>
      <div class="sideBar__item__name">追蹤名單</div>
    </div>
    <div class="sideBar__item">
      <span></span>
      <div class="sideBar__item__name">我按讚的文章</div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.sideBar {
  padding: 30px 25px;
  border: 2px solid #000400;
  background-color: #fff;

  &__item {
    display: flex;
    align-items: center;
    margin-top: 24px;

    span {
      display: block;
      width: 50px;
      height: 50px;
      background-color: #E2EDFA;
      border-radius: 50%;
      margin-right: 16px;
    }

    &__name {
      font-size: 16px;
      line-height: 24px;
      color: #000400;
    }
  }
}

.postBtn {
  width: 100%;
  height: 54px;
  background-color: #03438D;
  border: 2px solid #000400;
  box-shadow: -2px 2px 0px #000400;
  border-radius: 8px;
  padding: 16px;
  cursor: pointer;
  a {
    color: #fff;
  }
}
</style>
