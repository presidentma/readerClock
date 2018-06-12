<template>
<div class="slide-tab">
  <div class="left">
    <div class="left-top">
        <div class="avatar-wrapper">
        <img class="avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl">
    </div>
    </div>
    <!-- 菜单部分 -->
    <div class="menu-wrapper">
        <ul>
            <li class="menu" v-for="(item, index) in menus" :key="index"  @click="toMenu(item.url)">
                <div class="icon">
                    <img :src="item.icon" class="icon-item">
                </div>
                <div class="title">
                    {{item.title}}
                </div>
            </li>
        </ul>
        <!-- 底部菜单 -->
            <div class="foot-menu">
        <ul>
            <li class="item" v-for="(item,index) in foots" :key="index" @click="toMenu(item.url)">
                <div class="list">
                <img :src="item.icon" class="icon">
                <div class="title">{{item.title}}</div>
                </div>
            </li>
        </ul>
    </div>
    </div>

  </div>
</div>
</template>

<script>
import {images} from '../../common/js/image-base64'
export default {
  props: ['userInfo'],
  data () {
    return {
      menus: [
        {
          title: '打卡',
          icon: images.card,
          url: '/pages/sign/sign',
          index: 0
        },
        {
          title: '日志',
          icon: images.list,
          url: '/pages/record/record',
          index: 1
        },
        {
          title: '打卡',
          icon: images.card,
          url: '/pages/sign/sign',
          index: 2
        },
        {
          title: '日志',
          icon: images.list,
          url: '/pages/record/record',
          index: 3
        }
      ],
      foots: [
        {
          title: '设置',
          icon: images.setting,
          url: '/pages/setting/setting',
          index: 0
        },
        {
          title: '更多',
          icon: images.more,
          url: '/pages/more/more',
          index: 1
        }
      ]
    }
  },
  created () {
  },
  methods: {
    toMenu (url) {
      wx.navigateTo({ url })
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/image-base64'
    .slide-tab
        display flex
        width 600rpx
        height 1334rpx 
        margin 0 0 0 0
        .left
            flex 0 0 600rpx
            color $color-text
            
            .left-top
                height 400rpx
                background-size 100% 400rpx
                background-image: url($left-top-background)
                background-repeat no-repeat
                .avatar-wrapper
                    height 70rpx
                    width 70rpx
                    .avatar
                        position relative
                        height 68rpx
                        width 68rpx
                        top 160rpx
                        left 50rpx
                        border-radius: 50%
                        border:2px solid $color-border
            .menu-wrapper
                position relative
                display block
                top 50rpx
                background-color $color-background-menus
                .menu
                    display flex
                    position relative
                    left 70rpx
                    top 20rpx
                    .icon
                        flex 0 0 30rpx
                        vertical-align middle
                        width 64px
                        height 64px
                        .icon-item
                            width 32px
                            height 32px
                    .title
                        flex 1
                        margin-left 25rpx
                        vertical-align middle
                        font-size $font-size-large-x
                        font-weight 500
                        line-height 32px
                        font-family 'KaiTi'
                .foot-menu
                    position relative
                    color $color-text
                    top 100rpx
                    left 50rpx
                    .item
                        display inline-block
                        padding-left 25rpx
                        .list
                            display flex
                            .icon
                                flex 0 0 50rpx
                                width 32px
                                height 32px
                            .title
                                flex 1
                                margin-left 10rpx
                                font-size $font-size-large-x
                                font-weight 500
                                line-height 32px
                                font-family 'KaiTi'

</style>
