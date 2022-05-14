<template>
  <div class="container">
    <div class="row">
      <div class="col-md-8">
        <SelectGroup />
        <PostCard />
        <PostCard />
        <PostCard />
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
  created () {
    this.test();
  },
  methods: {
    test () {
      this.axios.get('https://thawing-retreat-19220.herokuapp.com/users').then((response) => {
        console.log(response)
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
