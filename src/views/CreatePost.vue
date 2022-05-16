<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <div class="create">
          <div class="create__header">張貼動態</div>
          <div class="create__content">
            <div class="form-group">
              <label for="postContent">貼文內容</label>
              <textarea class="form-control" id="postContent" rows="8" placeholder="輸入您的貼文內容" v-model="post.content"></textarea>
            </div>
            
            <div class="custom-file">
              <span>上傳圖片</span>
              <input type="file" class="custom-file-input" id="upload" accept="image/*" required @change="uploadFile">
            </div>
            
            <div class="priviewImg">
              <template v-if="previewImg">
                <span class="hasImg" :style="{ backgroundImage: `url(${previewImg})`}"></span>
              </template>
              <template v-else>
                <span class="noImg"></span>
              </template>
            </div>

            <div class="form-group">
              <button type="button" class="btn-post" @click.prevent="handleNewPost()">送出貼文</button>
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
  },
  data () {
    return {
      post: {
        user: '627a7e483daec2a5eda5f42c',
        content: '',
        photo: ''
      },
      file: null, // 準備拿 input type="file" 的值
      previewImg: ''
    }
  },
  methods: {
    handleNewPost () {
      if (this.previewImg === '') {
        alert('尚未上傳圖片')
        return false
      }
      const url = 'https://thawing-retreat-19220.herokuapp.com/posts';
      this.axios.post(url, this.post)
        .then((res) => {
          if (res.data.status === 'success') {
            this.post.content = ''
            this.post.photo = ''
            this.previewImg = ''
            alert('貼文送出成功');
          } else {
            alert('貼文送出失敗');
          }
        })
        .catch((error) => {
          console.log(error)
        })
    },
    async uploadFile (e) {
      this.file = e.target.files[0]; // input type="file" 的值
      let form = new FormData();
      form.append('image', this.file);

      const requestConfig = {
        method: "post",
        url: 'https://api.imgur.com/3/image',
        headers: {
          Authorization: 'Bearer 4745ecc03477331dd3f9c105ee69bc2d0008b807',
        },
        data: form,
      };

      await this.axios(requestConfig)
        .then((res) => {
          if (res.data.success) {
            this.previewImg = res.data.data.link;
            this.post.photo = this.previewImg;
          } else {
            alert('上傳失敗');
            return false
          }
        })
        .catch((err) => {
          console.log(err)
        })
    }
  }
}
</script>

<style lang="scss">
.custom-file {
  width: 128px;
  height: 32px;
  background-color: #000400;
  color: #fff;
  border-radius: 4px;
  padding: 4px;
  display: block;
  margin-bottom: 16px;
}
.custom-file-input {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
}

.priviewImg {
  border: 2px solid #000400;
  width: 100%;
  height: 157px;
  border-radius: 8px;
  overflow: hidden;
  .hasImg, .noImg {
    display: block;
    width: 100%;
    height: 157px;
  }
  .hasImg {
    background-size: cover;
    background-position: center;
  }
}
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
