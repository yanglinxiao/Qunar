<template>
  <div class="city-search">
    <input class="search-input"
           type="text"
           v-model="keyword"
           placeholder="输入城市名或拼音">
    <div class="search-result" ref="search" v-show="keyword">
      <ul>
        <li class="item border-bottom"
            v-for="item of searchResult"
            :key="item.id">
          {{item.name}}
        </li>
        <li class="item border-bottom"
            v-show="hasNoSearchResult">
          没有对应的搜索内容
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: "CitySearch",
  props: {
    searchResult: Array
  },
  data() {
    return {
      keyword: ''
    }
  },
  computed: {
    hasNoSearchResult () {
      return !this.searchResult.length
    }
  },
  watch: {
    keyword (newValue) {
      this.$emit('search', newValue)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl";
  .city-search
    height .72rem
    background-color $themeBgColor
    padding 0 .1rem
    .search-input
      width 100%
      height .64rem
      box-sizing border-box
      line-height .64rem
      background-color #ffffff
      padding .1rem
      text-align center
      color #666
      border-radius .06rem
    .search-result
      position absolute
      top 1.6rem
      left 0
      right 0
      bottom 0
      z-index 1
      overflow hidden
      background-color #eee
      width 100%
      .item
        padding-left .2rem
        line-height .6rem
        background-color #ffffff
</style>
