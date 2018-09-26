<template>
  <div class="main">
    <!-- 導覽列 -->
    <Navbar />
    <!-- banner -->
    <Banner />
    <!-- Main -->
    <template v-for="(item, key) in items">
      <MainBlock :data="item" :key="key" />
    </template>
    <div style="width: 100%; margin: 100px auto; display:flex; justify-content: center; align-items: center;">
      <div class="title3" :style="titleImg"></div>
    </div>
    <!-- 購物車產品 -->
    <ProductList :carts="carts" />
    <!-- Footer -->
    <Footer />
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import Banner from '@/components/Banner.vue'
import MainBlock from '@/components/MainBlock.vue'
import ProductList from '@/components/ProductList.vue'
import Footer from '@/components/Footer.vue'

import getTitleImg from '@/assets/imgs/home/lg-title3.svg'

const items = [
  {
    order: [1, 3, 2],
    picImg: require('@/assets/imgs/home/pic1.jpg'),
    lgTitleImg: require('@/assets/imgs/home/lg-title1.svg'),
    smTitleImg: require('@/assets/imgs/home/sm-title1.svg'),
    texts: `
      青山依舊在，幾度夕陽紅。慣看秋月春<br>
      一壺濁酒喜相逢，浪花淘盡英雄。是非<br>
      轉頭空，滾滾長江東逝水，白髮魚樵江<br>
      古今多少事，都付笑談中。<br>
      <br>
      是非成敗轉頭空。滾滾長江東逝水，白<br>
      髮魚樵江，古今多少事，都付笑談中。
    `
  },
  {
    order: [13, 12, 11],
    picImg: require('@/assets/imgs/home/pic2.jpg'),
    lgTitleImg: require('@/assets/imgs/home/lg-title2.svg'),
    smTitleImg: require('@/assets/imgs/home/sm-title2.svg'),
    texts: `
      青山依舊在，幾度夕陽紅。慣看秋月春<br>
      一壺濁酒喜相逢，浪花淘盡英雄。是非<br>
      轉頭空，滾滾長江東逝水，白髮魚樵江<br>
      古今多少事，都付笑談中。<br>
      <br>
      是非成敗轉頭空。滾滾長江東逝水，白<br>
      髮魚樵江，古今多少事，都付笑談中。
    `
  }
]

const carts = [
  {
    id: 0,
    name: '焦糖馬卡龍',
    price: 1050,
    pic: require('@/assets/imgs/home/cart1.jpg')
  },
  {
    id: 1,
    name: '焦糖馬卡龍',
    price: 1250,
    pic: require('@/assets/imgs/home/cart2.jpg')
  },
  {
    id: 2,
    name: '焦糖馬卡龍',
    price: 450,
    pic: require('@/assets/imgs/home/cart3.jpg')
  },
  {
    id: 3,
    name: '焦糖馬卡龍',
    price: 1050,
    pic: require('@/assets/imgs/home/cart1.jpg')
  },
  {
    id: 4,
    name: '焦糖馬卡龍',
    price: 1250,
    pic: require('@/assets/imgs/home/cart2.jpg')
  },
  {
    id: 5,
    name: '焦糖馬卡龍',
    price: 1000,
    pic: require('@/assets/imgs/home/cart3.jpg')
  }
]

export default {
  name: 'Home',
  components: {
    Navbar, Banner, MainBlock, ProductList, Footer
  },
  data () {
    return {
      items,
      carts
    }
  },
  computed: {
    titleImg () {
      return {
        'background-image': `url('${getTitleImg}')`
      }
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'src/assets/sass/mixins.sass'

.main
  +size(100%, 100%)
  margin: 0 auto
  .title3
    +bgset(89px, 327px)
    +center
</style>
