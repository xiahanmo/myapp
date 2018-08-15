<template>
  <ul class="list">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet'
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.list
  position absolute
  right 0.1rem
  top 1.58rem
  bottom 0
  width .4rem
  display flex
  flex-direction column
  justify-content center
  align-items center
  .item
    color $bgColor
    line-height .45rem
</style>
