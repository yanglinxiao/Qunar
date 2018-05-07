<template>
  <div class="city">
    <city-header></city-header>
    <city-search
      @search="handleSearch"
      :searchResult="searchResult"></city-search>
    <city-list
      :cityList="cityList"
      :hotCityList="hotCityList"
      :letter="letter"></city-list>
    <city-alphabet
      :cityList="cityList"
      @change="handleChange"></city-alphabet>
  </div>
</template>

<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: "City",
  components: {
    CitySearch,
    CityHeader,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cityList: {},
      hotCityList: [],
      letter: '',
      searchResult: [],
      timer: null
    }
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json')
        .then(this.getCityInfoSuccess)
    },
    getCityInfoSuccess (res) {
      if (res.data.status && res.status === 200) {
        const {data} = res.data
        this.cityList = data.cities
        this.hotCityList = data.hotCities
      }
    },
    handleChange (letter) {
      this.letter = letter
    },
    handleSearch (keyword) {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const searchResult = []
        if (keyword) {
          for (let item of Object.values(this.cityList)) {
            for (let subItem of item) {
              if (subItem.spell.indexOf(keyword) > -1 ||
                subItem.name.indexOf(keyword) > -1) {
                searchResult.push(subItem)
              }
            }
          }
        }
        this.searchResult = searchResult
      }, 100)
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style scoped>

</style>
