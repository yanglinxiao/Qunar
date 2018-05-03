<template>
  <div class="wrapper">
    <p class="category">热销推荐</p>
    <ul class="recommend-list">
      <li class="recommend border-bottom" v-for="item of list" :key="item.id">
        <img class="recommend-img" :src="item.imgUrl" alt="recommend-photo">
        <div class="recommend-info">
          <p class="title">{{item.title}}</p>
          <p class="desc">{{item.desc}}</p>
          <p class="check-detail">查看详情</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props: {
    list: Array
  }
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
