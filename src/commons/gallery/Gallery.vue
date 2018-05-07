<template>
  <div class="gallery" @click="handleGalleryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="item of imgList" :key="item.id">
          <img
            class="gallery-img"
            :src="item.url"
            alt="gallery">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommonGallery",
  props: {
    imgList: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .gallery >>> .swiper-container
    overflow inherit
  .gallery
    position fixed
    top 0
    bottom 0
    left 0
    right 0
    z-index 99
    display flex
    flex-direction column
    justify-content center
    background-color #000000
    .wrapper
      height 0
      padding-bottom 100%
      .gallery-img
        width 100%
        transform translateY(calc((100vw - 100%) / 2))
      .swiper-pagination
        bottom -3rem
        color #ffffff
</style>
