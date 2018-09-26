<template>
  <div class="productlist">
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="(cart, index) in carts" :key="index">
            <p class="today">本日精選</p>
            <i class="heart far fa-heart"></i>
            <img class="cartImg" :src="cart.pic" alt="cart.name">
            <div class="detail">
              <p class="name">{{ cart.name }}</p>
              <p class="price">NT$ {{ cart.price | currency }}</p>
            </div>
            <button class="addcart">加入購物車</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Swiper from 'swiper'
import 'swiper/dist/css/swiper.min.css'

export default {
  name: 'ProductList',
  props: {
    carts: Array
  },
  filters: {
    currency (num) {
      const n = Number(num)
      return `${n.toFixed(0).replace(/./g, (c, i, a) => {
        const currency = (i && c !== '.' && ((a.length - i) % 3 === 0) ? `, ${c}`.replace(/\s/g, '') : c)
        return currency
      })}`
    }
  },
  mounted () {
    new Swiper('.swiper-container', {
      loop: false,
      slidesPerView: 3,
      spaceBetween: 30,
      observer: true,
      observeParents: true
    })
  }
}
</script>
<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.productlist
  +size(100%, 500px)
  margin: 100px auto
  .swiper-container, .swiper-wrapper, .swiper-slide
    +size(100%)
  .swiper-slide
    +center
    flex-direction: column
    .today
      +size(36px, 106px)
      +center
      background-color: $primary
      color: $secondary
      writing-mode: vertical-rl
      letter-spacing: 3px
      line-height: 1
      font-weight: bold
      position: absolute
      top: 10px
      left: 10px
    .heart
      color: $primary
      position: absolute
      top: 50px
      right: 20px
    .cartImg
      +size(100%, 315px)
    .detail
      +size(100%, 56px)
      +center
      .name, .price
        height: 100%
        +center
        font-size: 20px
        color: $primary
        border-left: solid 1px $secondary
      .name
        flex: 1
      .price
        flex: 0.8
        font-weight: bold
        border-right: solid 1px $secondary
    .addcart
      +size(100%, 65px)
      font-size: 24px
      font-weight: bold
      background-color: $secondary
      color: $primary
</style>
