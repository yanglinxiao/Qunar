<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <img class="icon-img" :src="item.imgUrl" alt="icon">
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <!--<div class="swiper-pagination" slot="pagination"></div>-->
    </swiper>
  </div>
</template>

<script>
export default {
    name: "HomeIcons",
    props: {
        list: Array
    },
    data() {
      return {
        swiperOption: {}
      }
    },
  computed: {
    pages(){
      const pages = []
      this.list.forEach((item,index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
}
}
</script>

<style lang="stylus" scoped>
  @import "~@/styles/mixins.styl"
  .icons
    height 50vw
    overflow hidden
    background-color #ffffff
    .icon
      width 25%
      height 25vw
      float left
      display flex
      flex-direction column
      align-items center
      justify-content center
      .icon-img
        width 60%
      .icon-desc
        margin-top .1rem
        ellipsis();
</style>
