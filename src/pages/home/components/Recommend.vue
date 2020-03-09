<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data() {
    return {
      recommendList: [
        {
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1508/d9/12d379fbfee474d481da6e950b740ff3.water.jpg_200x200_4a3f867b.jpg',
        title: '增城金叶子温泉',
        desc: '沉浸在温泉里，想象自己是一只自由自在的鱼，游曳在温暖的水域。'
        },
        {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1508/d9/12d379fbfee474d481da6e950b740ff3.water.jpg_200x200_4a3f867b.jpg',
        title: '增城金叶子温泉',
        desc: '沉浸在温泉里，想象自己是一只自由自在的鱼，游曳在温暖的水域。'
        },
        {
        id: '0003',
        imgUrl: 'https://imgs.qunarzz.com/sight/p0/1508/d9/12d379fbfee474d481da6e950b740ff3.water.jpg_200x200_4a3f867b.jpg',
        title: '增城金叶子温泉',
        desc: '沉浸在温泉里，想象自己是一只自由自在的鱼，游曳在温暖的水域。'
        },
    ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .1rem
        border-radius: .06rem
        color: #fff
</style>
