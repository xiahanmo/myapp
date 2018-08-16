<template>
  <div class="banner">
    <div class="bannerImg-wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item,index) of list" :key="index">
          <img :src="item" alt="">
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
    <ul>
      <li>产品编号</li>
      <li><span class="iconfont banner-icon">&#xe692;</span>{{listNum}}</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'DetailBanner',
  data () {
    return {
      list: ['https://img1.qunarzz.com/p/tts9/1708/23/8e372e48c656b102.jpg_r_640x420x90_9b14366e.jpg', 'https://img1.qunarzz.com/p/tts4/1801/bd/b1d05fc1258e8802.jpg_r_640x420x90_d391b0f3.jpg'],
      swiperOption: {
        loop: true,
        pagination: '.swiper-pagination',
        paginationType: 'fraction'
      }
    }
  },
  computed: {
    listNum () {
      return this.list.length
    }
  }
}
</script>
<style lang="stylus" scoped>
.banner
  position relative
  .bannerImg-wrapper
    width 100%
    height 0
    padding-bottom 55%
    img
      width 100%
    .swiper-pagination-fraction
      right 0
      bottom 1rem
      width .64rem
      z-index 2
      color #ffffff
  ul
    display flex
    height .64rem
    line-height .64rem
    background linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,0.8))
    overflow hidden
    position absolute
    left 0
    right 0
    bottom 0
    z-index 1
    li
      color #ffffff
      .banner-icon
        margin-right .2rem
      &:nth-child(1)
        flex 1
        float left
        padding-left .2rem
      &:nth-child(2)
        width 1.08rem
        float right

</style>
