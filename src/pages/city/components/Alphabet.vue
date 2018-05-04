<template>
  <ul class="city-alphabet">
    <li class="item"
        v-for="(value,key) of cityList"
        :key="key"
        :ref="key"
        @click="handleClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >{{key}}</li>
  </ul>
</template>

<script>
  export default {
    name: "CityAlphabet",
    props: {
      cityList: Object,
    },
    data() {
      return {
        letters: [],
        headerSearchHeight: '',
        startY: '',
        itemLineHeight: '',
        timer: null
      }
    },
    methods: {
      handleClick(e) {
        this.$emit('change',e.target.innerText);
      },
      handleTouchStart() {
        this.status = true
      },
      handleTouchMove(e) {
        if (this.status) {
          if (this.timer) {
            clearTimeout(this.timer);
          }
          this.timer = setTimeout(() => {
            const touchY = e.touches[0].clientY;
            const index = Math.floor((touchY - this.headerSearchHeight - this.startY) / this.itemLineHeight)
            if (index >= 0 && index < this.letters.length) {
              this.$emit('change',this.letters[index]);
            }
          },100)
        }
      },
      handleTouchEnd() {
        this.status = false
      },
      splitPx(data) {
        return data.substring(0,data.indexOf('px'));
      }
    },
    updated (){
      const startLetter = this.$refs['A'][0]
      this.headerSearchHeight = this.splitPx(window.getComputedStyle(startLetter.offsetParent).top)
      this.startY = startLetter.offsetTop
      this.itemLineHeight = this.splitPx(window.getComputedStyle(startLetter).lineHeight)
      this.letters = Object.keys(this.cityList)
    }
  }
</script>

<style lang="stylus" scoped>
  @import "../../../styles/variable.styl"
  .city-alphabet
    position absolute
    top 1.6rem
    right 0
    bottom 0
    display flex
    flex-direction column
    justify-content center
    .item
      line-height .4rem
      color $themeBgColor
      text-align center
      padding-right .1rem
</style>
