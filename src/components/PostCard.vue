<template>
  <div class="postCard">
    <div class="postCard__user d-flex">
      <span class="postCard__user__img"></span>
      <div class="postCard__user__info d-flex flex-column">
        <span class="postCard__user__info__name">邊緣小杰</span>
        <span class="postCard__user__info__time">2022/1/10 12:00</span>
      </div>
    </div>
    <p class="postCard__content">外面看起來就超冷.... <br>我決定回被窩繼續睡....>.&lt;</p>
    <span class="postCard__img"></span>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
.postCard {
  background-color: #fff;
  box-shadow: 0px 3px 0px #000400;
  border: 2px solid #000400;
  border-radius: 8px;
  padding: 24px;
  margin-top: 16px;
  &__user {
    span {
      display: block;
    }
    &__img {
      width: 45px;
      height: 45px;
      border-radius: 50%;
      border: 2px solid #000400;
      background-color: #E2EDFA;
      margin-right: 16px;
    }
    &__info {
      span {
        display: block;
      }
      &__name {
        font-size: 16px;
        line-height: 24px;
        color: #000400;
        text-align-last: left;
      }
      &__time {
        font-size: 12px;
        line-height: 20px;
        color: #9B9893;
      }
    }
  }
  &__content {
    font-size: 16px;
    line-height: 24px;
    color: #000400;
    margin-bottom: 0;
    text-align-last: left;
    margin-top: 16px;
  }
  &__img {
    display: block;
    width: 100%;
    height: 157px;
    border: 2px solid #000400;
    border-radius: 8px;
    background-color: gray;
    margin-top: 16px;
  }
}
</style>
