<template>
    <div class="header">
        <div class="header-left">
            <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link tag="div" class="header-right" to="/city">
            {{this.city}}
            <span class="iconfont arrow-icon">&#xe64a;</span>
        </router-link>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
   .header
      display: flex
      height: .86rem
      line-height:.86rem
      background: $bgColor
      color: #ffffff
      .header-left
        width: .64rem
        float: left
        .back-icon
          text-align: center
          font-size: .4rem
      .header-input
        height: .64rem
        line-height: .64rem
        flex: 1
        background: #ffffff
        border-radius: .1rem
        margin-top: .12rem
        margin-left: .2rem
        color: #cccccc
        padding-left: .2rem
      .header-right
        min-width: 1.24rem
        padding: 0 .1rem
        float: right
        text-align: center
        .arrow-icon
          font-size: .24rem
          margin-left: -.02rem
</style>
