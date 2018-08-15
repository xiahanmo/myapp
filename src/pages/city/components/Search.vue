<template>
    <div class="header">
      <input class="search-input" type="text" placeholder="输入城市名或拼音">
    </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.header
  height $headerHeight
  line-height $headerHeight
  background $bgColor
  text-align center
  color #ffffff
  font-size .32rem
  position relative
  padding 0 .2rem
  margin auto
  .search-input
    padding 0 .1rem
    display inline-block
    width 100%
    border-radius .1rem
    text-align center
    color #666666
    height .62rem
    line-height .62rem
    box-sizing border-box
</style>
