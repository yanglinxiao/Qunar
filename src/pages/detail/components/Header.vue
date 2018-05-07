<template>
  <div>
    <div class="detail-header"
         :style="opacityStyle"
         v-show="showDetailHeader">
      <router-link to="/">
        <i class="iconfont icon-left"></i>
      </router-link>
      <span class="title">景点详情</span>
    </div>
    <router-link
      tag="div"
      to="/"
      class="back-btn"
      v-show="!showDetailHeader">
      <i class="iconfont icon-left"></i>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "DetailHeader",
  data () {
    return {
      showDetailHeader: false,
      opacityStyle: ''
    }
  },
  methods: {
    handleScroll () {
      const scrollTop = document.documentElement.scrollTop
      if (scrollTop > 60 && scrollTop < 140) {
        const opacity = scrollTop / 140
        this.opacityStyle = {
          opacity: opacity > 1 ? 1 : opacity
        }
        this.showDetailHeader = true
      }
      if (scrollTop < 60) {
        this.showDetailHeader = false
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl"
  .detail-header
    text-align center
    background-color $themeBgColor
    height $headerHeight
    line-height $headerHeight
    color $themeFontColor
    position fixed
    top 0
    left 0
    right 0
    z-index 1
    opacity 0
    .icon-left
      position absolute
      top 0
      left .1rem
      color $themeFontColor
    .title
      font-size .32rem
  .back-btn
    position absolute
    z-index 1
    left .2rem
    display inline-block
    width .7rem
    height .7rem
    line-height .7rem
    margin-top: .2rem
    text-align center
    background-color rgba(0, 0, 0, .5)
    border-radius 50%
    .icon-left
      color #ffffff
</style>
