<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="( page,index ) of pages" :key="index">
        <dl class="icon" v-for="item in page" :key="item.iid">
          <dd><img :src="item.src" alt=""></dd>
          <dt>优惠券优惠券优惠券优惠券</dt>
        </dl>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  computed: {
    pages () {
      const pages = []
      this.iconLists.forEach((item, index) => {
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
      },
      iconLists: [{
        iid: '0001',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0002',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0003',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0004',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0005',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0006',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0007',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0008',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      },
      {
        iid: '0009',
        src: 'https://img12.360buyimg.com/jrpmobile/jfs/t3991/64/2521945388/12110/93c0139/58d1e462Ncf294123.png?width=132&height=132'
      }]
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
