<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <SelectGroup />
        <template v-for="item in posts">
          <PostCard :info="item" />
        </template>
        
        <template v-if="false">
          <NoPost />
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
import SelectGroup from '../components/SelectGroup.vue'
import NoPost from '../components/NoPost.vue'
import PostCard from '../components/PostCard.vue'

export default {
  name: 'HomeView',
  components: {
    SideBar,
    SelectGroup,
    NoPost,
    PostCard
  },
  data () {
    return {
      posts: []
    }
  },
  created () {
    this.handleGetPosts();
  },
  methods: {
    handleGetPosts () {
      const url = 'https://thawing-retreat-19220.herokuapp.com/posts';
      this.axios.get(url)
        .then((res) => {
          if (res.data.status === 'success') {
            this.posts = res.data.data
            console.log('this.posts', this.posts)
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
</style>
