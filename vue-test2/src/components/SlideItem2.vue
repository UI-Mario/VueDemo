<template>
  <div class="slide-item">
    <div class="img-contain">
      <router-link :to="'/subject/'+movieitem.id">
        <img
          class="poster"
          :src="movieitem.images.medium"
          alt=""
          referrerpolicy ="never"
        >
      </router-link>
    </div>
    <div class="contain">
      {{movieitem.title}}
      <span class="rate">{{movieitem.rating.average}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Slideitem2',
  props: ['movieitem'],
  data () {
    return {}
  }
}
</script>

<style scoped lang="less" rel="stylesheet/less">
.slide-item {
  width: 115px;
  height: 210px;
  // background-color: aqua;
  .img-contain {
    width: 100%;
    height: 170px;
    img {
      width: 100%;
    }
  }
  .contain {
    width: 100%;
    text-align: center;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    font-size: 13px;
    color: #3377aa;
  }
  .rate {
    margin: 0;
    font-size: 13px;
    color: #e09015;
    margin-left: 5px;
  }
}
</style>
