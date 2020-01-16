<template>
  <div class="home">
    <div class="main" v-loading="loading">
      <SlideMode1 :movielist="movielist" />
      <SlideMode2 />
      <Gallery />
      <p>ToDo</p>
      <p>ToDo</p>
      <p>ToDo</p>
    </div>
    <div class="ad">
      <p>11111111111111111111</p>
    </div>
  </div>
</template>

<script>
import SlideMode1 from '@/components/SlideMode1.vue'
import SlideMode2 from '@/components/SlideMode2.vue'
import Gallery from '@/components/Gallery.vue'

import { getAllNowMovie } from '@/network/request'

export default {
  name: 'home',
  components: {
    SlideMode1,
    SlideMode2,
    Gallery
  },
  data () {
    return {
      movielist: [],
      loading: false
    }
  },
  created () {
    getAllNowMovie().then(res => {
      // console.log('this is getallnowmovie')
      console.log(res.data.subjects)
      this.movielist = res.data.subjects
      this.loading = false
    })
  },
  mounted () {
    this.loading = true
  }
}
</script>

<style scoped lang="less" rel="stylesheet/less">
.home {
  // background-color: aliceblue;
  display: flex;
  flex-direction: row;
  margin-top: 10px;
  .main {
    width: 675px;
    // background-color: blue;
    margin-left: 135px;
  }
  .ad {
    width: 300px;
    margin-left: 60px;
    background-color: blueviolet;
  }
}
</style>
