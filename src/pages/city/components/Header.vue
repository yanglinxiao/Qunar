<template>
  <div class="city-header">
    <router-link to="/">
      <i class="iconfont icon-left"></i>
    </router-link>
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
      color $themeFontColor
    .title
      font-size .32rem
</style>
