<template>
  <div>
    <div class="title">热销推荐</div>
    <ul class="item">
      <li class="border-bottom" v-for="item in recommendList" :key="item.rid">
        <img :src="item.src" alt="">
        <dl>
          <dt>{{item.title}}</dt>
          <dd>{{item.place}}</dd>
          <dd>{{item.price}}</dd>
        </dl>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        rid: '0001',
        src: 'https://imgs.qunarzz.com/douxing/i1/1711/f6/71d34beed7078a02.jpg',
        title: '普吉岛【双体帆船包船】私密独享出海浮潜海钓一日游可登岛包专车接送',
        price: '¥4449',
        place: '地区：普吉岛'
      }]
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
