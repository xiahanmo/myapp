<template>
  <div>
    <detail-header></detail-header>
    <detail-banner :list="gallaryImgs" :sightName="sightName"></detail-banner>
    <detail-list :list="categoryList"></detail-list>
  </div>
</template>
<script>
import DetailHeader from './components/Header'
import DetailBanner from './components/Banner'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailHeader,
    DetailBanner,
    DetailList
  },
  data () {
    return {
      gallaryImgs: [],
      sightName: '',
      categoryList: []
    }
  },
  mounted () {
    this.detailAjaxData()
  },
  methods: {
    detailAjaxData () {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.detailAjaxDataSuccess)
    },
    detailAjaxDataSuccess (res) {
      let msg = res.data
      console.log(msg.data['' + this.$route.params.id + ''])
      if (msg.ret && msg.data) {
        this.gallaryImgs = msg.data['' + this.$route.params.id + ''].gallaryImgs
        this.sightName = msg.data['' + this.$route.params.id + ''].sightName
        this.categoryList = msg.data['' + this.$route.params.id + ''].categoryList
      }
    }
  }
}
</script>
<style lang="stylus" scoped>

</style>
