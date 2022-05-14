<template>
  <div class="selectGroup">
    <div class="row">
      <div class="col-md-4">
        <div class="selectGroup__menu">
          <select class="custom-select">
            <option value="1" selected>最新貼文</option>
            <option value="2">最舊貼文</option>
          </select>
        </div>
      </div>
      <div class="col-md-8">
        <div class="input-group">
          <input type="text" class="form-control" placeholder="搜尋貼文">
          <div class="input-group-append">
            <span class="input-group-text" id="basic-addon2"><i class="fa fa-search"></i></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.custom-select {
  border: 2px solid #000400;
  height: 100%;
}

.input-group-text {
  background-color: #03438D;
  color: white;
  border: none;
  border-radius: 0;
}

.input-group {
  border: 2px solid #000400;
}

.form-control {
  border: none;
}
</style>
