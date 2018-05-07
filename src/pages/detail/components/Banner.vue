<template>
  <div class="detail-banner">
    <img class="banner-img"
         :src="bannerList[0].url"
         @click="handleBannerClick"
         alt="banner">
    <div class="banner-info">
      <span class="left">岭南印象园门票</span>
      <div class="right">
        <i class="iconfont icon-search"></i>
        <span class="banner-count">39</span>
      </div>
    </div>
    <common-gallery :imgList="bannerList"
                    v-show="showGallery"
                    @close="handleGalleryClose"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from 'commons/gallery/Gallery'
export default {
  name: "DetailBanner",
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      bannerList: [
        {
          id: 1,
          url: 'http://img1.qunarzz.com/sight/p0/1802/af/afd475218580d73ca3.img.jpg_r_800x800_8c2da002.jpg'
        },
        {
          id: 2,
          url: 'http://img1.qunarzz.com/sight/p0/1802/89/8954b2fa3daf91d3a3.img.jpg_r_800x800_d4d01624.jpg'
        }
      ]
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .detail-banner
    height 0
    padding-bottom 55%
    overflow hidden
    position relative
    .banner-img
      width 100%
    .banner-info
      display flex
      align-items center
      position absolute
      left 0
      right 0
      bottom 0
      color #ffffff
      padding .1rem
      background-image linear-gradient(top, rgba(0, 0, 0, 0),rgba(0, 0, 0, .8))
      .left
        flex 1
        font-size .32rem
      .right
        height .5rem
        line-height .5rem
        padding 0 .2rem
        background-color rgba(0, 0, 0, .8)
        border-radius .06rem
        opacity .8
</style>
