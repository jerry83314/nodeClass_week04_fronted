<template>
  <div class="nav">
    <div class="container">
      <div class="d-flex justify-content-between">
        <div class="nav__title">
          <router-link to="/">
            MetaWall
          </router-link>
        </div>
        <div class="nav__user">
          <span class="nav__user__img"></span>
          <div class="d-flex flex-column justify-content-center">
            <div class="nav__user__name">Member</div>
            <span class="nav__user__border"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.nav {
  padding: 12px;
  border-bottom: 2px solid #000400;
  margin-bottom: 48px;
  background-color: #fff;

  &__title {
    font-size: 26px;
    line-height: 36px;
    a {
      color: #000400;
    }
  }

  &__user {
    display: flex;
    align-items: center;

    span {
      display: block;
    }

    &__img {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      background-color: #E2EDFA;
      border: 2px solid #000400;
      margin-right: 10px;
    }

    &__name {
      font-size: 16px;
      line-height: 19px;
      color: #000400;
    }

    &__border {
      width: 100%;
      height: 2px;
      background-color: #000400;
    }
  }
}
</style>
