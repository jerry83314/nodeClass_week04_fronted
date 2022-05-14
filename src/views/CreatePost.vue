<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <div class="create">
          <div class="create__header">張貼動態</div>
          <div class="create__content">
            <div class="form-group">
              <label for="postContent">貼文內容</label>
              <textarea class="form-control" id="postContent" rows="8" placeholder="輸入您的貼文內容"></textarea>
            </div>
            <div class="form-group text-left">
              <button type="button" class="btn btn-dark">上傳圖片</button>
            </div>
            <div class="form-group">
              <input type="text" class="form-control" placeholder="圖片網址">
            </div>
            <div class="form-group">
              <button type="button" class="btn-post">送出貼文</button>
            </div>
          </div>
        </div>
      </div>
      <div class="col-md-4">
        <SideBar />
      </div>
    </div>
  </div>
</template>

<script>
import SideBar from '../components/SideBar.vue'

export default {
  name: 'HomeView',
  components: {
    SideBar
  }
}
</script>

<style lang="scss">
.create {
  &__header {
    width: 100%;
    height: 56px;
    padding: 16px;
    font-size: 20px;
    line-height: 24px;
    color: #000400;
    text-align: center;
    border: 2px solid #000400;
    background-color: #fff;
  }
  &__content {
    margin-top: 16px;
    padding: 32px;
    box-shadow: 0px 3px 0px #000400;
    border: 2px solid #000400;
    border-radius: 8px;
    background-color: #fff;
    label {
      margin-bottom: 4px;
      font-size: 16px;
      line-height: 24px;
      color: #000400;
      display: block;
      text-align: left;
    }
    .form-control {
      border: 2px solid #000400;
    }
    .btn {
      font-size: 16px;
      line-height: 24px;
      padding: 4px 32px;
      background-color: #000400;
      border-radius: 4px;
    }
    .btn-post {
      background-color: #A8B0B9;
      border: 2px solid #000400;
      border-radius: 8px;
      padding: 16px 130px;
      margin-top: 16px;
    }
  }
}
</style>
