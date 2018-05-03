<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="page of pages">
        <div class="icon" v-for="item of page" :key="item.id">
          <img class="icon-img" :src="item.imgUrl" alt="icon">
          <p class="icon-desc">{{item.iconDesc}}</p>
        </div>
      </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
    export default {
        name: "HomeIcons",
        data(){
          return {
            swiperOption: {
              pagination: '.swiper-pagination'
            },
            iconList: [
              {
                id: 1,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                iconDesc: '景点门票'
              },
              {
                id: 2,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                iconDesc: '必游榜单'
              },
              {
                id: 3,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                iconDesc: '动植物园'
              },
              {
                id: 4,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/54/35899492b1302802.png',
                iconDesc: '公园'
              },
              {
                id: 5,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
                iconDesc: '游船游艇'
              },
              {
                id: 6,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/bd/9f7b9b2b60c1502.png',
                iconDesc: '踏青赏花'
              },
              {
                id: 7,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
                iconDesc: '名胜古迹'
              },
              {
                id: 8,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
                iconDesc: '一日游'
              },
              {
                id: 9,
                imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
                iconDesc: '全部玩乐'
              },
            ]
          }
        },
      computed: {
          pages(){
            const pages = [];
            this.iconList.forEach((item,index) => {
              const page = Math.floor(index / 8);
              if(!pages[page]){
                pages[page] = [];
              }
              pages[page].push(item);
            })
            return pages;
          }
      }
    }
</script>

<style lang="stylus" scoped>
  @import "~@/styles/mixins.styl"
  .icons >>> .swiper-container-horizontal > .swiper-pagination-bullets
    bottom 1px
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
        width 50%
      .icon-desc
        ellipsis();
</style>
