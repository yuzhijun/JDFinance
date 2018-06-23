<template>
    <div class="header">
     城市选择
       <router-link tag="div" class="iconfont header-back" to="/">&#xe624;</router-link>
    </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position: relative
    height: $HeaderHeight
    line-height: $HeaderHeight
    overflow: hidden
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
