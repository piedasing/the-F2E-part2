<template>
  <div class="mainblock">
    <div class="pic" :style="picSrc" />
    <div class="title" :style="titleSrc" />
    <div class="texts" :style="{'order': data.order[2]}" v-html="data.texts"></div>
  </div>
</template>

<script>
export default {
  name: 'Mainblock',
  props: {
    data: Object
  },
  computed: {
    titleSrc () {
      return {
        'background-image': `url('${this.data.lgTitleImg}')`,
        'order': this.data.order[1]
      }
    },
    picSrc () {
      // return {
      //   'background-image': `url('${this.data.picImg}')`,
      //   'order': this.data.order[0]
      // }
      let obj = {
        'background-image': `url('${this.data.picImg}')`,
        'order': this.data.order[0]
      }
      if (this.data.order[0] % 10 === 1) {
        obj = {
          ...obj,
          'transform': 'scale(1.1) translateX(10px)'
        }
      } else if (this.data.order[0] % 10 === 2) {
        obj = {
          ...obj,
          'margin': '0 50px',
          'transform': 'scale(1.1)'
        }
      } else {
        obj = {
          ...obj,
          'margin-left': '50px',
          'transform': 'scale(1.1) translateX(-10px)'
        }
      }
      return obj
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.mainblock
  +size(100%, 420px)
  display: flex
  margin: 100px auto
  padding: 0 50px
  background-color: $secondary
  .pic
    +bgset(420px)
    transition: 0.5s
    &:hover
      transform: scale(1.2) !important
      opacity: 0.7
  .title
    +bgset(89px, 305px)
    transform: translateY(-20px)
  .texts
    flex: auto
    height: 100%
    +center
    color: #8DA291
    writing-mode: vertical-rl
    font-size: 16px
    line-height: 2.8
</style>
