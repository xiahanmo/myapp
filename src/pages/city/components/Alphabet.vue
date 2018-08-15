<template>
  <ul class="list">
    <li class="item"
    v-for="(item,index) of letters"
    :key="index"
    :ref="item"
    :data-id='index'
    @click="handleLetterClick"
    @touchstart="handleLetterStart"
    @touchmove="handleLetterMove"
    @touchend="handleLetterEnd"
    >{{item}}</li>
  </ul>
</template>>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false
    }
  },
  mounted () {
    // console.log(this.cities)
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleLetterStart (e) {
      this.touchStatus = true
    },
    handleLetterMove (e) {
      console.log(e.touches[0])
      // this.$emit('change', e.target.innerText)
      if (this.touchStatus) {
        const startY = this.$refs['A'][0].offsetTop
        const touchY = e.touches[0].clientY - 79
        const index = Math.floor((touchY - startY) / 20)
        if (index >= 0 && index < this.letters.length) {
          this.$emit('change', this.letters[index])
        }
      }
    },
    handleLetterEnd (e) {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~@styles/varibles.styl';
.list
  position absolute
  right 0
  top 1.58rem
  bottom 0
  width .5rem
  display flex
  flex-direction column
  justify-content center
  align-items center
  .item
    color $bgColor
    padding .05rem .1rem
</style>
