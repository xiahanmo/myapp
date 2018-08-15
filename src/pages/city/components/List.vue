<template>
  <div class="wrapper" ref="ref">
    <div>
      <h4 class="border-topbottom">当前城市</h4>
      <ul>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
      </ul>
      <h4 class="border-topbottom">热门城市</h4>
      <ul>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
        <li><span>北京</span></li>
      </ul>
      <h4 class="border-topbottom">A</h4>
      <div class="item">
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
        <p class="border-bottom">alias</p>
      </div>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new BScroll(this.$refs.ref)
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
