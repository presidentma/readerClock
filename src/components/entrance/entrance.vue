<template>
<div class="entrance">
  <scroll-view scroll-y="1" class="scroll-h" :style="{height: pageH}" @scroll="scrollY">
<top :user-info="userInfo"></top>
<div class="list-wrapper">
  <reList :record-list="recordList"></reList>
</div>
</scroll-view>
</div>
</template>

<script>
import top from '@/components/top/top'
import reList from '@/components/list/list'
import {images} from '../../common/js/image-base64'
import store from '@/pages/counter/store'

export default {
  props: ['userInfo'],
  data () {
    return {
      recordList: [
        {
          index: 1,
          title: '第一个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 2,
          title: '第二个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 3,
          title: '第三个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 4,
          title: '第四个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 5,
          title: '第五个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 6,
          title: '第6个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 7,
          title: '第7个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 8,
          title: '第8个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 9,
          title: '第9个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 10,
          title: '第10个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 11,
          title: '第11个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        },
        {
          index: 12,
          title: '第12个记录',
          contents: '6人vw7rtw34rt36rt',
          avatar: images.avatar,
          time: '02/20-15:05'
        }
      ],
      pageH: store.state.pageHeight
    }
  },
  components: {
    top,
    reList
  },
  methods: {
    scrollY (e) {
      let scrollY = e.mp.detail.deltaY
      this.$emit('scrollY', scrollY)
    }
  },
  created () {
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/variables';
    .entrance
        width 750rpx
        .scroll-h
          position relative
          .list-wrapper
            width 750rpx
</style>
