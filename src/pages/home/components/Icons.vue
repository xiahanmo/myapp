<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="( page,index ) of pages" :key="index">
        <dl class="icon" v-for="item in page" :key="item.id">
          <dd><img :src="item.imgUrl" alt=""></dd>
          <dt>{{item.desc}}</dt>
        </dl>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
@import '~@styles/mixins.styl';
  .icons
    overflow hidden
    height 0
    padding-bottom 50%
    .icon
      width 25%
      height 0
      padding-bottom 25%
      float left
      dd
        padding-top .2rem
        img
          width 50%
          display block
          margin auto
      dt
        text-align center
        margin-top .2rem
        color $darkTextColor
        ellipsis()
</style>
