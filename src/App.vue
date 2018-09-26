<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from '@/pages/Home.vue'

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>

<style lang="sass">
@import 'src/assets/sass/mixins.sass'

*
  margin: 0
  padding: 0
  text-decoration: none
  list-style: none
  outline: none
  border: none
  box-sizing: border-box
  font-family: 'Microsoft JhengHei'

#app
  +size(100%)
  max-width: 1024px
  margin: 0 auto
</style>
