<template>
  <div>
    <banner 
    :sightName="sightName"
    :bannerImg="bannerImg"
    :gallaryImgs="gallaryImgs"
    ></banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import Banner from '@/pages/detail/components/Banner'
import DetailHeader from '@/pages/detail/components/Header'
import DetailList from '@/pages/detail/components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    Banner,
    DetailHeader,
    DetailList,
  },
  data() {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      list: []
    }
  },
  methods: {
    getDetailInfo() {
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc(res) {
      res = res.data
      if(res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted() {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>