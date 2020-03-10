<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list 
    :hotCities="hotCities" 
    :cities="cities"
    :letter="letter"
    ></city-list>
    <city-alphabet 
    :cities="cities"
    @change="handleLetterChange"
    ></city-alphabet>
  </div>
</template>

<script>
import axios from 'axios'
import CityHeader from '@/pages/city/components/Header'
import CitySearch from '@/pages/city/components/Search'
import CityList from '@/pages/city/components/List'
import CityAlphabet from '@/pages/city/components/Alphabet'
export default {
  name: 'City',
  data() {
    return {
      hotCities: [],
      cities: {},
      letter: '',
    }
  },
  methods: {
    getCityInfo() {
      axios.get('/api/city.json')
      .then(this.getCityInfoSucc)
    },
    getCityInfoSucc(res) {
      res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    handleLetterChange(letter) {
      this.letter = letter
    }
  },
  mounted() {
    this.getCityInfo()
  },
  components:{
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet,
  }
}
</script>

<style lang="stylus" scoped>
</style>
