<template>
  <div>
    <banner></banner>
    <detail-header></detail-header>
    <div class="content"></div>
  </div>
</template>

<script>
import Banner from '@/pages/detail/components/Banner'
import DetailHeader from '@/pages/detail/components/Header'
export default {
  name: 'Detail',
  components: {
    Banner,
    DetailHeader,
  },
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>