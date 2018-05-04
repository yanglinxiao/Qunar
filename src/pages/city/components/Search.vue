<template>
  <div class="city-search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
  export default {
    name: "CitySearch"
  }
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl";
  .city-search
    height .72rem
    background-color $themeBgColor
    padding 0 .1rem
    .search-input
      width 100%
      height .64rem
      box-sizing border-box
      line-height .64rem
      background-color #ffffff
      padding .1rem
      text-align center
      color #666
      border-radius .06rem
</style>
