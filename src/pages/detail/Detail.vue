<template>
  <div class="detail">
    <detail-header></detail-header>
    <detail-banner
      :galleryImgs="galleryImgs"
      :bannerImg="bannerImg"
      :sightName="sightName"></detail-banner>
    <detail-list :list="categoryList"></detail-list>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: "Detail",
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      categoryList: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json', {
        params: this.$route.params.id
      }).then(this.getDetailInfoSuccess)
    },
    getDetailInfoSuccess (res) {
      const {data} = res.data
      if (res.data.status && res.status === 200) {
        console.log(data)
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.galleryImgs = data.galleryImgs
        this.categoryList = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
</style>
