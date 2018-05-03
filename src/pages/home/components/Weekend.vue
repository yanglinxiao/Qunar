<template>
  <div class="wrapper">
    <p class="category">周末去哪儿</p>
    <ul class="weekend-list">
      <li class="weekend border-bottom">
        <img src="http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg" alt="">
        <p class="title">广州必游TOP10</p>
        <p class="desc">感受现代与传统相融合的广州</p>
      </li>
      <li class="weekend border-bottom">
        <img src="http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg" alt="">
        <p class="title">广州必游TOP10</p>
        <p class="desc">感受现代与传统相融合的广州</p>
      </li>
      <li class="weekend border-bottom">
        <img src="http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg" alt="">
        <p class="title">广州必游TOP10</p>
        <p class="desc">感受现代与传统相融合的广州</p>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "HomeWeekend"
    }
</script>

<style lang="stylus" scoped>
  @import "~@/styles/mixins.styl"
  .wrapper
    .category
      line-height .8rem
      background-color #eee
      padding-left .2rem
      font-size .3rem
    .weekend-list
      .weekend
        overflow hidden
        img
          width 100%
          height 2.8rem
        p
          ellipsis()
          &.title
            padding .2rem .1rem .1rem
          &.desc
            padding .1rem .1rem .2rem
</style>
