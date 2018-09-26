<template>
  <div class="banner">
    <div class="image" :style="bannerImg" />
    <div class="types">
      <div class="today" :style="bannerImg1">
        <div class="text" :class="{'onClicked': now === 'today'}" v-on:click="now = 'today'">本日精選</div>
      </div>
      <div class="popular" :style="bannerImg2">
        <div class="text" :class="{'onClicked': now === 'popular'}" v-on:click="now = 'popular'">人氣推薦</div>
      </div>
      <div class="new" :style="bannerImg3">
        <div class="text" :class="{'onClicked': now === 'new'}" v-on:click="now = 'new'">新品上市</div>
      </div>
    </div>
  </div>
</template>

<script>
import getBannerImg from '@/assets/imgs/home/banner.jpg'
import getBannerImg1 from '@/assets/imgs/home/banner1.jpg'
import getBannerImg2 from '@/assets/imgs/home/banner2.jpg'
import getBannerImg3 from '@/assets/imgs/home/banner3.jpg'

export default {
  name: 'Banner',
  data () {
    return {
      now: 'today'
    }
  },
  computed: {
    bannerImg () {
      return {
        'background-image': `url('${getBannerImg}')`
      }
    },
    bannerImg1 () {
      return {
        'background-image': `url('${getBannerImg1}')`
      }
    },
    bannerImg2 () {
      return {
        'background-image': `url('${getBannerImg2}')`
      }
    },
    bannerImg3 () {
      return {
        'background-image': `url('${getBannerImg3}')`
      }
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.banner
  +size(100%, auto)
  margin-bottom: 240px
  padding: 0 50px
  position: relative
  .image
    +bgset(100%, 500px)
  .types
    +size(80%, auto)
    +center
    margin: 0 auto
    position: absolute
    bottom: -180px
    left: calc((100% - 80%) / 2)
    .today, .popular, .new
      //- 放背景圖
      +bgset(256px)
      div
        //- 顯示垂直排列的文字及顏色遮罩
        +size(100%)
        +center
        writing-mode: vertical-lr
        letter-spacing: 5px
        font-size: 20px
        font-weight: bold
        background-color: rgba(63, 93, 69, 0.8)
        color: #FFFFFF
        transition: 0.8s
        &:hover, &.onClicked
          background-color: rgba(255,225,128,0.8)
          color: $primary
    .popular
      border-left: solid 1px #FFFFFF
      border-right: solid 1px #FFFFFF
</style>
