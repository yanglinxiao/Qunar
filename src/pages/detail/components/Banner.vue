<template>
  <div class="detail-banner">
    <img class="banner-img"
         :src="bannerImg"
         @click="handleBannerClick"
         alt="banner">
    <div class="banner-info">
      <span class="left">{{this.sightName}}</span>
      <div class="right">
        <i class="iconfont icon-search"></i>
        <span class="banner-count">{{this.galleryImgs.length}}</span>
      </div>
    </div>

    <fade>
      <common-gallery :imgList="galleryImgs"
                      v-show="showGallery"
                      @close="handleGalleryClose"></common-gallery>
    </fade>
  </div>
</template>

<script>
import CommonGallery from 'commons/gallery/Gallery'
import Fade from 'commons/fade/Fade'
export default {
  name: "DetailBanner",
  props: {
    sightName: {
      type: String,
      default () {
        return ''
      }
    },
    bannerImg: {
      type: String,
      default () {
        return ''
      }
    },
    galleryImgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  components: {
    CommonGallery,
    Fade
  },
  data () {
    return {
      showGallery: false
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
