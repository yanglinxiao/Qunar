<template>
  <div class="wrapper">
    <p class="category">热销推荐</p>
    <ul class="recommend-list">
      <li class="recommend border-bottom">
        <img class="recommend-img" src="http://img1.qunarzz.com/sight/p0/1602/b2/b2af115356f50f6590.img.jpg_200x200_d3daf0af.jpg" alt="">
        <div class="recommend-info">
          <p class="title">岭南印象园</p>
          <p class="desc">很好玩很好玩很好玩很好玩</p>
          <p class="check-detail">查看详情</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "HomeRecommend"
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
    .recommend-list
      .recommend
        display flex
        flex-direction row
        align-items center
        padding .1rem
        .recommend-img
          width 2rem
          height 2rem
        .recommend-info
          overflow hidden
          & > p + p
            margin-top .3rem
          margin-left .2rem
          .title
            ellipsis()
            font-size .3rem
          .desc
            ellipsis()
            color #999
          .check-detail
            color #ffffff
            background-color orange
            display inline-block
            padding .1rem .2rem
</style>
