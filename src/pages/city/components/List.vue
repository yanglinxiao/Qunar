<template>
  <div class="city-list" ref="wrapper">
    <div>
      <div class="area">
        <p class="category">当前城市</p>
        <div class="city">{{this.city}}</div>
      </div>
      <div class="area">
        <p class="category">热门城市</p>
        <ul class="hot-city-list">
          <li class="city"
              v-for="item of hotCityList"
              :key="item.id"
              @click="handleCityClick(item.name)">{{item.name}}</li>
        </ul>
      </div>
      <div class="area"
           v-for="(value,key) of cityList"
           :key="key"
           :ref="key"
           >
        <p class="category">{{key}}</p>
        <ul class="letter-city-list">
          <li class="letter-city border-bottom"
              v-for="item of value"
              :key="item.id"
              @click="handleCityClick(item.name)">{{item.name}}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import {mapMutations, mapState} from 'vuex'
export default {
  name: "CityList",
  props: {
    cityList: Object,
    hotCityList: Array,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter (newValue) {
      if (newValue) {
        this.scroll.scrollToElement(this.$refs[newValue][0])
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "../../../styles/mixins.styl"
  .city-list
    position absolute
    left 0
    top 1.6rem
    right 0
    bottom 0
    width 100%
    overflow hidden
    .area
      .category
        category(.6rem)
      .city
        padding .1rem
        border 1px solid #666
        border-radius .06rem
        width 28%
        text-align center
        margin .2rem 0 .2rem .2rem
        box-sizing border-box
      .hot-city-list
        display flex
        flex-wrap wrap
      .letter-city-list
        .letter-city
          height .6rem
          line-height .6rem
          padding-left .2rem
</style>
