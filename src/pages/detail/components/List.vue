<template>
  <div class="detail-list">
    <div class="item border-bottom"
        v-for="(item,index) of list"
        :key="index">
      <div class="item-header">
        <span class="item-icon"></span>
        <span class="item-title">{{item.title}}</span>
      </div>
      <div v-if="item.children" class="item-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailList",
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-header
    .item-icon
      display inline-block
      width .36rem
      height .36rem
      position relative
      top .08rem
      left .1rem
      background url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -.45rem no-repeat
      margin-right .1rem
      background-size .4rem 3rem
    .item-title
      height .6rem
      line-height .6rem
      font-size .3rem
  .item-children
    padding 0 .2rem
</style>
