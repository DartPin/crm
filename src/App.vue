<template>
  <div id="app">
    <GoodsMain></GoodsMain>
  </div>
</template>

<script>
import GoodsMain from "./Goods/GoodsMain/GoodsMain.vue"

export default {
  name: 'app',
  data () {
    return {
     
    }
  },
  components:{
    GoodsMain
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}


</style>
