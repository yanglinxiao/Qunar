<template>
  <div class="detail">
    <detail-header></detail-header>
    <detail-banner></detail-banner>
    <detail-list :list="list"></detail-list>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
export default {
  name: "Detail",
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [
        {
          title: '成人票',
          children: [
            {
              title: '体育中心店'
            },
            {
              title: '北京路店'
            }
          ]
        },
        {
          title: '学生票'
        },
        {
          title: '儿童票'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .detail
    height 20rem
</style>
