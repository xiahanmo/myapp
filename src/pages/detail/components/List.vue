<template>
  <div class="list">
    <ul >
      <li v-for="(item,index) of list" :key="index">
        <div class="title border-bottom">{{item.title}}</div>
        <div class="child border-bottom" v-if="item.children">
          <detail-list :list="item.children"></detail-list>
        </div>

      </li>

    </ul>
  </div>
</template>
<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.list
  ul
    color $bgColor
    .title
      padding .2rem
    .child
      padding-left .2rem
</style>
