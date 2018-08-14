<template>
<div class="wrapper">
  <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.sid">
        <img :src="item.src" alt="">
      </swiper-slide>

      <div class="swiper-pagination" slot="pagination"></div>
  </swiper>
</div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  props: {

  },
  data () {
    return {
      swiperOption: {
        loop: true,
        pagination: '.swiper-pagination',
        clickable: true
      },
      swiperList: [{
        'sid': '0001',
        'title': '0001',
        'src': 'https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/anquan_20180716.png'
      }, {
        'sid': '0002',
        'title': '0002',
        'src': 'https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/dujia_shuqi_banner_20180710.jpg'
      }, {
        'sid': '0003',
        'title': '0003',
        'src': 'https://source.qunarzz.com/site/images/wap/home/recommend/iphoneplus/20180716_wap_11043.jpg'
      }]

    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background #ffffff
  .wrapper
    overflow hidden
    width 100%
    height 0
    padding-bottom 24.53%
    // heigh 24.53vw
    .swiper-pagination-bullet-active
      background #ffffff
    img
      width 100%
</style>
