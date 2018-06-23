<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for="(page,index) of pages" :key="index">
                <div class="icon" v-for="item of page" :key="item.id">
                    <div class="icon-img">
                    <img class="icon-imgcontent" :src="item.imgUrl"/>
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
             <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-pagination-bullets
    bottom: 0rem
  .icons >>> .swiper-container
    overflow: inherit
    width: 100%
    height: 0
    padding-bottom: 52%
  .icon
    position: relative
    overflow: hidden
    height: 0
    float: left
    width: 25%
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: 0
      left: 0
      bottom: .44rem
      right: 0
      box-sizing: border-box
      padding: .1rem
      .icon-imgcontent
        height: 100%
        display: block
        margin: 0 auto
    .icon-desc
      width: 100%
      position: absolute
      bottom: 0
      left: 0
      line-height: .44rem
      height: .44rem
      color: $darkTextColor
      text-align: center
      ellipsis()
</style>
