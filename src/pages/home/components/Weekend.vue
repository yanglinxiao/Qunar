<template>
  <div class="wrapper">
    <p class="category">周末去哪儿</p>
    <ul class="weekend-list">
      <li class="weekend border-bottom" v-for="item of list" :key="item.id">
        <img :src="item.imgUrl" alt="weekend-photo">
        <p class="title">{{item.title}}</p>
        <p class="desc">{{item.desc}}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HomeWeekend",
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@/styles/mixins.styl"
  .wrapper
    .category
      category(.8rem)
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
