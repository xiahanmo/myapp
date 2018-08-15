<template>
  <div class="wrapper" ref="ref">
    <div class="content">
      <h4 class="border-topbottom">当前城市</h4>
      <ul>
        <li><span>{{this.currentCity}}</span></li>
      </ul>
      <h4 class="border-topbottom">热门城市</h4>
      <ul>
        <li v-for="item of hot" :key="item.id" @click="handleCityClick(item.name)">
          <span>{{item.name}}</span>
        </li>
      </ul>
      <div v-for="(item,index) of cities" :key="index">
        <h4 class="border-topbottom" :ref="index">{{index}}</h4>
        <div class="item" v-for="items of item" :key="items.id">
          <p class="border-bottom">{{items.name}}</p>
        </div>
      </div>

    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
import {mapState, mapMutations} from 'vuex'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    })
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.ref)
  },
  methods: {
    handleCityClick (city) {
      // this.$store.dispatch('changeCity', city)
      this.changeCityCommit(city)
      // 编程式导航，js控制页面跳转
      this.$router.push('/')
    },
    ...mapMutations(['changeCityCommit'])
  },
  watch: {
    letter () {
      console.log(this.letter)
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }

  }
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.wrapper
  position absolute
  top 0
  left 0
  bottom 0
  right 0
  overflow hidden
  margin-top 1.68rem
  .content
    // overflow-y scroll
    h4
      background #eeeeee
      color $darkTextColor
      line-height .54rem
      padding-left 0.2rem
    ul
      padding .1rem .6rem .1rem .1rem
      overflow hidden
      li
        width 33.33%
        box-sizing border-box
        float left
        span
          display block
          padding .1rem 0
          margin .1rem
          border-radius .06rem
          text-align center
          border .02rem solid #cccccc
    .item
     p
      padding .2rem
</style>
