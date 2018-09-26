<template>
  <div class="navbar">
    <div class="navTitle">
      <div class="logoImg" :style="logoImg"></div>
    </div>
    <div class="navLinks">
      <a href="javascript:;" class="navLink">首頁</a>
      <a href="javascript:;" class="navLink">甜點</a>
      <a href="javascript:;" class="navLink">登入</a>
      <a href="javascript:;" class="navLink">
        <i class="fas fa-shopping-cart"/>
      </a>
    </div>
  </div>
</template>

<script>
import getLogoImg from '@/assets/imgs/home/logo-all-dark.svg'

export default {
  name: 'Navbar',
  computed: {
    logoImg () {
      return {
        'background-image': `url('${getLogoImg}')`
      }
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.navbar
  +size(100%, 100px)
  +center
  margin: 0 auto
  padding: 0 50px
  .navTitle
    flex: none
    +size(40%, 100%)
    +center
    justify-content: flex-start
    .logoImg
      +bgset(220px, 40px)
  .navLinks
    flex: auto
    height: 100%
    +center
    justify-content: flex-end
    .navLink
      margin-left: 60px
      color: $primary
</style>
