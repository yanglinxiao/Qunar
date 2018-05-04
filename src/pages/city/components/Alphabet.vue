<template>
  <ul class="city-alphabet">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
  export default {
    name: "CityAlphabet"
  }
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl"
  .city-alphabet
    position absolute
    top 1.6rem
    right 0
    bottom 0
    display flex
    flex-direction column
    justify-content center
    .item
      line-height .4rem
      color $themeBgColor
      text-align center
      padding-right .1rem
</style>
