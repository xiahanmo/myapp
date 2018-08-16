<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
      </div>
    <div class="header-right">
      <router-link to="/city">
        <span class="iconfont arrow-font">{{this.city}}</span>
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </router-link>
    </div>
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default {
  name: 'HomeHeader',
  props: {
    city: String
  },
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
@import '~@styles/varibles.styl'
@import '~@styles/mixins.styl'
  .header
    height .86rem
    line-height .86rem
    display flex
    background $bgColor
    color #ffffff
    .header-left
      float left
      width .64rem
      text-align center
      .back-icon
        text-align center
        font-size .4rem
    .header-right
      float right
      min-width 1.24rem
      text-align center
      .arrow-font
        color #ffffff
      .arrow-icon
        margin-left -.04rem
        font-size .24rem
        color #ffffff
    .header-input
      flex 1
      background #ffffff
      border-radius .1rem
      box-sizing border-box
      margin-top .12rem
      margin-left .2rem
      height .64rem
      color #cccccc
      line-height .64rem
      padding-left .2rem

</style>
