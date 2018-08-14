<template>
    <div>
        <home-header :city='city'></home-header>
        <home-swiper :list='swiperList'></home-swiper>
        <home-icons :list='iconList'></home-icons>
        <home-recommend :list='recommendList'></home-recommend>
    </div>

</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/recommend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: []
    }
  },
  mounted () {
    this.homeAjaxData()
  },
  methods: {
    homeAjaxData () {
      axios.get('/api/index.json')
        .then(this.resolve)
    },
    resolve (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) { // 判断返回的数据正确
        const data = res.data
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
      }
    }
  }
}
</script>

<style scoped>

</style>
