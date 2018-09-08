<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1603/85/85aa0c000578a01e90.water.jpg_600x330_6dddcf68.jpg">
      <div class="banner-info">
        <div class="banner-title">拙政园(AAAA)</div>
        <div class="banner-number"><span class="iconfont banner-icon">&#xe62e;</span>39</div>
      </div>
    </div>
    <common-gallary :imgs="imgs" @close="handleGallaryClose" v-show="showGallary"></common-gallary>
  </div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1807/92/92f857221c01059fa3.img.jpg_r_800x800_77f2770c.jpg', 'http://img1.qunarzz.com/sight/p0/1707/ee/eefec632f78e4a6fa3.img.jpg_r_800x800_02f8cd55.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>
<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #fff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
          padding-right: .08rem
</style>
