<template>
    <div class="header">
      <router-link to="/">
        <span class="iconfont back-icon">&#xe624;</span>
      </router-link>
      <span class="title">
        城市选择
      </span>

    </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.header
  height $headerHeight
  line-height $headerHeight
  background $bgColor
  text-align center
  font-size .32rem
  position relative
  color #ffffff
  .back-icon
    position absolute
    top 0
    left 0
    width .64rem
    display block
    color #ffffff
</style>
