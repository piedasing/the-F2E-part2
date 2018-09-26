<template>
  <div class="myfooter">
    <div class="mailForm">
      <div class="title">
        <div class="logo" :style="logoImg" />
        <p>訂閱你我的甜蜜郵件</p>
      </div>
      <div class="inputbox">
        <div class="mailIcon">
          <i class="fas fa-envelope"></i>
        </div>
        <input type="mail">
        <a href="javascript:;" class="send">
          <i class="fas fa-arrow-right"></i>
        </a>
      </div>
    </div>
    <!-- detail -->
    <div class="detail">
      <div class="logo" :style="logoImg2" />
      <div class="title" :style="titleImg" />
      <div class="contact">
        <p>07-1234-5678</p>
        <p>sweetaste@email.com</p>
        <p>800 高雄市新興區幸福路 520 號</p>
        <div class="community">
          <div class="line" :style="lineIcon" />
          <div class="fb" :style="fbIcon" />
        </div>
      </div>
      <p class="copyright">2018 Sweetaste* All Rights Reserved</p>
    </div>
  </div>
</template>

<script>
import getLogoImg from '@/assets/imgs/home/logo-light.svg'
import getLogoImg2 from '@/assets/imgs/home/logotype.svg'
import getTitleImg from '@/assets/imgs/home/sm-footer-title.svg'
import getLineIcon from '@/assets/imgs/home/ic-line@.svg'
import getFbIcon from '@/assets/imgs/home/ic-facebook.svg'

export default {
  name: 'Footer',
  computed: {
    logoImg () {
      return {
        'background-image': `url('${getLogoImg}')`
      }
    },
    logoImg2 () {
      return {
        'background-image': `url('${getLogoImg2}')`
      }
    },
    titleImg () {
      return {
        'background-image': `url('${getTitleImg}')`
      }
    },
    lineIcon () {
      return {
        'background-image': `url('${getLineIcon}')`
      }
    },
    fbIcon () {
      return {
        'background-image': `url('${getFbIcon}')`
      }
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.myfooter
  +size(100%, auto)
  .mailForm
    +size(100%, 116px)
    +center
    background-color: $primary
    .title, .inputbox
      flex: 1
      height: 56px
      +center
    .title
      color: $secondary
      font-size: 24px
      .logo
        +bgset(40px)
        margin-right: 20px
    .inputbox
      justify-content: flex-start
      .mailIcon
        flex: none
        +size(50px, 100%)
        +center
        padding: 0 20px
        background-color: #FFFFFF
        color: $primary
        font-size: 24px
      input
        flex: none
        +size(50%, 100%)
        // flex: auto
        // height: 100%
      a.send
        flex: none
        +size(64px, 100%)
        +center
        background-color: #FFE180
        color: $primary
  //--------------------------------
  .detail
    +size(100%, 340px)
    background-color: $secondary
    position: relative
    .logo, .title, .contact, .copyright
      position: absolute
    .logo
      +bgset(171px, 26px)
      top: 38px
      left: 122px
    .title
      +bgset(59px, 218px)
      top: 38px
      right: 122px
    .contact
      bottom: 30px
      left: 122px
      p
        color: $primary
        line-height: 1.5
        letter-spacing: 1px
      .community
        +center
        justify-content: flex-start
        margin-top: 30px
        .fb, .line
          +bgset(32px)
          margin: 0 4px
    .copyright
      color: $primary
      bottom: 30px
      right: 122px
</style>
