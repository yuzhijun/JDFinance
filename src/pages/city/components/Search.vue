<template>
    <div>
      <div class="search">
        <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音"/>
      </div>
      <div class="search-content" ref="search" v-show="keyword">
        <ul>
          <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item)">{{item}}</li>
          <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
        </ul>
      </div>
    </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        if (!this.keyword) {
          this.list = []
          return
        }
        for (let i in this.cities) {
          this.cities[i].forEach(element => {
            if (element.spell.indexOf(this.keyword) > -1 || element.name.indexOf(this.keyword) > -1) {
              result.push(element.name)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    overflow: hidden
    height: .72rem
    background: $bgColor
    padding: 0 .1rem
    .search-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      padding: 0 .1rem
  .search-content
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.58rem
    left: 0
    right: 0
    bottom: 0
    background: #eeeeee
    .search-item
      line-height: .62rem
      padding-left: .2rem
      color: #666
      background: #ffffff
</style>
