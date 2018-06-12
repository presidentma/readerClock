<template>
  <div class="top">
    <img class="avatar" v-if="userInfo.avatarUrl" :src="userInfo.avatarUrl"  @click="spread">
  </div>
</template>

<script>
import store from '../../pages/counter/store'
export default {
  props: ['userInfo'],
  data () {
    return {
      side: false
    }
  },
  methods: {
    spread () {
      store.commit('changeside')
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../common/stylus/variables';
  .top
    background-color $color-background-top
    width 750rpx
    height 84rpx
    .avatar
      width: 64rpx
      height: 64rpx
      margin: 10rpx 0 10rpx 16rpx
      border-radius: 50%
</style>
