<template>
  <div class="container">
      <!-- ref不可用 -->
<!--  使用小程序的scroll-view -->
<scroll-view scroll-x="1" scroll-left="600" upper-threshold="80" class="scroll-lr" style=" white-space: nowrap">
<div class="scroll-item position" :style="{top: topChange}">
    <slide :user-info="userInfo">
</slide>
</div>
<div class="scroll-item">
<entrance :user-info="userInfo" @scrollY="scrollY"></entrance>
</div>
</scroll-view>
  </div>
</template>

<script>
import card from '@/components/card'
import entrance from '@/components/entrance/entrance'
import slide from '@/components/slide/slide'
import store from '../counter/store'

export default {
  data () {
    return {
      userInfo: {},
      side: store.state.side,
      leftOffset: 600
    }
  },

  components: {
    card,
    entrance,
    slide
  },
  methods: {
    bindViewTap () {
      const url = '../logs/logs'
      wx.navigateTo({ url })
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              this.userInfo = res.userInfo
            }
          })
        }
      })
    },
    scrollY (Y) {
      return Y
    }
  },
  created () {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo()
    // console.log(store.state.side)
    this.touch = {}
  },
  watch: {
  },
  computed: {
    topChange () {
      let Y = this.scrollY
      return Y
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/variables';
  .container
    width 750rpx
    margin 0
    padding 0
    .scroll-lr
      overflow hidden
      top 0
      z-index 99
      .scroll-item
        display inline-block
        vertical-align top
        top 0
      .position
        position relative
</style>
