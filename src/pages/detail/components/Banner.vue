<template>
    <div>
      <div class="banner" @click="handleBannerClick">
        <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1506/30/7a528fae12c17e6e29d5d13a9d9813ee.water.jpg_600x330_866232e3.jpg"/>
        <div class="banner-info">
          <div class="banner-title">大连圣海洋公园</div>
          <div class="banner-number"><span class="iconfont banner-icon">&#xe626;</span>39</div>
        </div>
      </div>
      <common-gallery :imgs="imgs" v-show="isShowGallery" @change="handleChange"></common-gallery>
    </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1506/ba/d25df17c5f6542e03695ba7b8bf766c4.water.jpg_r_800x800_ce4f6947.jpg']
    }
  },
  computed: {
    isShowGallery () {
      return this.showGallery
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleChange () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      bottom: 0
      right: 0
      line-height: .6rem
      color: #ffffff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        margin-right: .2rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
