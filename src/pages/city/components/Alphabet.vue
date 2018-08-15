<template>
  <ul class="list">
    <li class="item" v-for="(item,index) of cities" :key="index">{{index}}</li>
  </ul>
</template>>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
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
