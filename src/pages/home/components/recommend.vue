<template>
  <div>
    <div class="title">热销推荐</div>
    <ul class="item">
      <router-link tag='li' class="border-bottom" v-for="item in list" :key="item.id" :to="'/detail/'+item.id">
        <img :src="item.imgUrl" alt="">
        <dl>
          <dt>{{item.desc}}</dt>
          <dd>{{item.title}}</dd>
          <dd>$455</dd>
        </dl>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  },
  data () {
    return {

    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
@import '~@styles/mixins.styl';
  .title
    background #eeeeee
    text-indent 0.2rem
    line-height 0.8rem
  .item
    li
      padding .2rem
      display flex
      img
        width: 1.7rem
        height: 1.7rem
      dl
        flex 1
        min-width 0
        margin-left 0.2rem
        dt
          ellipsis()
          font-size .32rem
          color $baseColor
          margin-top .1rem
        :nth-child(2)
          margin-top .4rem
          color $darkTextColor
        :nth-child(3)
          color red
          margin-top .2rem

</style>
