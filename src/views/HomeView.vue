<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <div class="selectGroup">
          <div class="row">
            <div class="col-md-4">
              <div class="selectGroup__menu">
                <select class="custom-select" v-model="sort">
                  <option value="" selected>最新貼文</option>
                  <option value="asc">最舊貼文</option>
                </select>
              </div>
            </div>
            <div class="col-md-8">
              <div class="input-group">
                <input type="text" class="form-control" placeholder="搜尋貼文" v-model="searchWord">
                <div class="input-group-append" @click.prevent="handleGetPosts()">
                  <span class="input-group-text" id="basic-addon2"><i class="fa fa-search"></i></span>
                </div>
              </div>
            </div>
          </div>
        </div>
        <template v-if="posts.length === 0">
          <NoPost />
        </template>
        <template v-else>
          <template v-for="item in posts">
            <PostCard :info="item" />
          </template>
        </template>
      </div>
      <div class="col-md-4">
        <SideBar />
      </div>
    </div>
  </div>
</template>

<script>
import SideBar from '../components/SideBar.vue'
import NoPost from '../components/NoPost.vue'
import PostCard from '../components/PostCard.vue'

export default {
  name: 'HomeView',
  components: {
    SideBar,
    NoPost,
    PostCard
  },
  data() {
    return {
      posts: [],
      sort: '',
      searchWord: ''
    }
  },
  created() {
    this.handleGetPosts();
  },
  methods: {
    handleGetPosts() {
      const url = `https://thawing-retreat-19220.herokuapp.com/posts?timeSort=${this.sort}&q=${this.searchWord}`;
      this.axios.get(url)
        .then((res) => {
          if (res.data.status === 'success') {
            this.posts = res.data.data
          } else {
            return false
          }
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>

<style lang="scss" scoped>
.container {
  padding-bottom: 48px;
}

.custom-select {
  border: 2px solid #000400;
  height: 100%;
}

.input-group-append {
  cursor: pointer;
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
