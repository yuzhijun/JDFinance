<template>
    <div>
      <div class="banner" @click="handleBannerClick">
        <img class="banner-img" :src="this.bannerImg"/>
        <div class="banner-info">
          <div class="banner-title">{{this.sightName}}</div>
          <div class="banner-number"><span class="iconfont banner-icon">&#xe626;</span>39</div>
        </div>
      </div>
      <common-gallery :imgs="gallaryImgs" v-show="isShowGallery" @change="handleChange"></common-gallery>
    </div>
</template>

<script>
import CommonGallery from 'common/gallery/Gallery'
export default {
  name: 'DetailBanner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  components: {
    CommonGallery
  },
  data () {
    return {
      showGallery: false
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
