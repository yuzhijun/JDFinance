<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
                <img class="item-img" :src="item.imgUrl"/>
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
  props: {
    recommendList: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    height: .8rem
    width: 100%
    text-indent : .2rem
    background: #eeeeee
    margin-top: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    .item-img
      width: 1.5rem
      height: 1.5rem
      padding: .2rem
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
        font-size: .28rem
        color: #cccccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .22rem
        background: #ff9300
        padding: 0 .2rem
        color: #ffffff
        border-radius: .07rem
</style>
