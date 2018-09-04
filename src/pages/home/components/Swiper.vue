<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for='item of swiperList' :key='item.id'>
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '001',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1808/fd/fddc5309111a0402.jpg_750x200_e7b93551.jpg'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    /*overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 31.25%*/
    background: #eee
    .swiper-img
      width: 100%
</style>
