<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" alt="banner">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
    export default {
        name: "HomeSwiper",
        data(){
          return {
            swiperOption: {
              autoplay: 3000,
              pagination: '.swiper-pagination',
              loop: true
            },
            swiperList: [
              {
                id: 1,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/68/30167ce000808f02.jpg_640x200_9d5df966.jpg'
              },
              {
                id: 2,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/ff/86d79cd397cbe802.jpg_640x200_6877eed5.jpg'
              },
              {
                id: 3,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/10/3ee6df72beb86402.jpg_640x200_6bc5c502.jpg'
              }
            ]
          }
        }
    }
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color #ffffff
  .wrapper
    width 100%
    height 0
    overflow hidden
    padding-bottom 31.25%
    background-color #eee
    .swiper-img
      width 100%
</style>
