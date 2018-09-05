<template>
    <div class="header">
      城市选择
      <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
    </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    line-height: $headerHeight
    height: $headerHeight
    over-flow: hidden
    text-align: center
    background: $bgColor
    font-size: .32rem
    color: #fff
    .header-back
      position: absolute
      top: 0
      left: 0
      width: .32rem
      text-align: center
      font-size: .4rem
      color: #fff
      padding-left: .15rem
</style>
