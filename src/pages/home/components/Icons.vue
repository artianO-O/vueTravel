<template>
  <div class="icons">
    <swiper class="wrapper">
      <!-- slides -->
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data() {
    return {
      iconList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        desc: '热门景点',
      }
      , {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
        desc: '广州必游',
      }
      , {
        id: '0003',
        imgUrl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20193/184e261814a5d07a5d3d08cd29cf590d.png',
        desc: '长隆度假区',
      }
      , {
        id: '0004',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
        desc: '广州塔',
      }
      , {
        id: '0005',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/3e/86314b2af03b7502.png',
        desc: '珠江夜游',
      }
      , {
        id: '0006',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png',
        desc: '泡温泉',
      }
      , {
        id: '0007',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/c1/6f15f887179fa002.png',
        desc: '岭南印象园',
      }
      , {
        id: '0008',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1803/fa/2548667cb6e902.png',
        desc: '动植物园',
      }
      , {
        id: '0009',
        imgUrl: 'https://imgs.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        desc: '一日游玩',
      }]
    }
  },
  computed: {
    pages() {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]){
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages;
    }
  }
};
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl';
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      position: relative;
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkTextColor
        ellipsis()
</style>

