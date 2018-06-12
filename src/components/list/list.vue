<template>
<div class="list">
      <ul>
        <li v-for="(item, index) in recordList" :key="index" class="item-wrapper">
          <div class="avatar">
            <img :src="item.avatar" class="img">
          </div>
          <div class="contents-wrapper">
            <div class="centents">
              <div class="title">{{item.title}}</div>
            <div class="time">{{item.time}}</div>
            </div>
            <div class="content">{{item.contents}}</div>
          </div>
        </li>
      </ul>     
</div>
</template>

<script>

export default {
  props: ['recordList'],
  data () {
    return {
    }
  },
  computed: {
  },
  methods: {
  },
  created () {
  }
}
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/variables';
  .list
    width 750rpx
    .item-wrapper
      width: 750rpx
      height 120rpx
      display: flex
      flex-grow: row no-wrap
      justify-content: space-between
      padding: 30rpx
      box-sizing: border-box
      align-items: center
      border-bottom: 1px solid #F2F2F2
      .avatar
        flex 0 0 120rpx
        width: 100rpx
        height: 100rpx
        position: relative
        .img
          width: 100%
          height: 100%
          border-radius 50%
      .contents-wrapper
          flex 1
          position relative
          margin-left 50rpx
          .centents
            display flex
            margin auto
            overflow:hidden
            text-overflow ellipsis
            white-space:nowrap
            .title
              flex 0 0 300rpx
              font-size 36rpx
              font-weight 600
              font-family 'FangSong'
            .time
              flex 1
              margin-left 50rpx
              font-size 28rpx
              line-height 60rpx
              color $color-text-contents
          .content
            color $color-text-contents
            font-size 32rpx
                
            
</style>
