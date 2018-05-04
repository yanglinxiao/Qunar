 <template>
  <div class="header">
    <div class="header-left">
      <i class="iconfont icon-left"></i>
    </div>
    <div class="header-input">
      <i class="iconfont icon-search"></i>
      <span>输入目的地/景点</span>
    </div>
    <div class="header-right">
      <span>城市</span>
      <i class="iconfont icon-down"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeHeader"
}
</script>

<style lang="stylus" scoped>
  @import "~@/styles/variable.styl"
  .header
    height .86rem
    display flex
    align-items center
    background-color $themeBgColor
    color $themeFontColor
    .header-left
      margin-left .1rem
    .header-input
      flex 1
      background-color #ffffff
      height .64rem
      line-height .64rem
      border-radius .1rem
      margin 0 .1rem
      padding-left.2rem
      color #ccc
    .header-right
      margin-right .1rem
      .icon-down
        position relative
        top 1px
</style>
