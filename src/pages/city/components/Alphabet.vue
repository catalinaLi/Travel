<template>
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item" :ref="item"
        @touchstart.prevent="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        @click="handleAplhabetClick"
    >{{item}}</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchstart: false,
      startY: 0,
      timer: null
    }
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
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleAplhabetClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchstart = true
    },
    handleTouchMove (e) {
      if (this.touchstart) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 74 /* 74为顶部toolbar的长度 */
          const idx = Math.floor((touchY - this.startY) / 20)
          if (idx >= 0 && idx < this.letters.length) {
            this.$emit('change', this.letters[idx])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchstart = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .list
    display: flex
    flex-direction: column
    justify-content: center
    position: absolute
    top: 1.58rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor
</style>
