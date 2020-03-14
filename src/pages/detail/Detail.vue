<template>
  <div>
    <banner></banner>
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
export default {
  name: 'Detail',
  components: {
    Banner,
    DetailHeader,
    DetailList,
  },
  data() {
    return {
      list: [{
        title: '成人票',
        children: [{title: '成人三馆联票',
        children: [{title: '成人三馆联票-某馆'}]},
        {title: '成人五馆联票'}],
      },{
        title: '学生票'
      },{
        title: '儿童票'
      },
      {
        title: '特惠票'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>