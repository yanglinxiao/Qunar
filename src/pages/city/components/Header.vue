<template>
  <div class="city-header">
     <i class="iconfont icon-left"></i>
     <span class="title">城市选择</span>
  </div>
</template>

<script>
  export default {
    name: "CityHeader"
  }
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl"
  .city-header
    text-align center
    background-color $themeBgColor
    height $headerHeight
    line-height $headerHeight
    color $themeFontColor
    .icon-left
      position absolute
      top 0
      left .1rem
    .title
      font-size .32rem
</style>
