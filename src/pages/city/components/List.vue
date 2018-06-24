<template>
    <div class="list" ref="wrapper">
      <div>
        <div class="area">
          <div class="title border-topbottom">当前城市</div>
          <div class="button-list">
            <div class="button-wrapper">
              北京
            </div>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">热门城市</div>
           <div class="button-list">
            <div class="button-wrapper">
              北京
            </div>
            <div class="button-wrapper">
              上海
            </div>
            <div class="button-wrapper">
              福建
            </div>
            <div class="button-wrapper">
              深圳
            </div>
            <div class="button-wrapper">
              杭州
            </div>
          </div>
        </div>
        <div class="area">
          <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
          </div>
               <div class="title border-topbottom">A</div>
          <div class="item-list">
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
            <div class="item border-bottom">
              阿拉尔
            </div>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CityList',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color: #ccc
    &:after
      border-color: #ccc
  .border-bottom
    &:before
      border-color: #ccc
  .list
    overflow: hidden
    position: absolute
    left: 0
    top: 1.58rem
    right: 0
    bottom: 0
    .title
      line-height: .54rem
      background: #eeeeee
      padding-left: .2rem
      color: $darkTextColor
      font-size: .26rem
    .button-list
      overflow: hidden
      padding: .1rem .6rem .1rem .1rem
      .button-wrapper
        width: 30%
        float: left
        text-align: center
        margin: .1rem
        border: .02rem solid #cccccc
        padding: .1rem 0
        border-radius: .06rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem
</style>
