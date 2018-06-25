<template>
    <div>
      <router-link tag="div" class="header-abs" to="/" v-show="showAbs">
        <span class="iconfont back-icon">&#xe624;</span>
      </router-link>
      <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
          <router-link tag="div" class="iconfont header-back" to="/">&#xe624;</router-link>
          景点详情
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const scrollTop = document.body.scrollTop || document.documentElement.scrollTop
      if (scrollTop > 60) {
        let opacity = scrollTop / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: absolute
    left: .2rem
    top: .2rem
    width: .8rem
    height: .8rem
    line-height: .8rem
    border-radius: .4rem
    background: rgba(0, 0, 0, .8)
    text-align: center
    .back-icon
      color: #ffffff
      font-size: .4rem
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right: 0
    height: $HeaderHeight
    line-height: $HeaderHeight
    text-align: center
    color: #ffffff
    background: $bgColor
    font-size: .32rem
    .header-back
      position: absolute
      width: .64rem
      text-align: center
      font-size: .4rem
      left: 0
      top: 0
</style>
