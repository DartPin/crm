<template>
  <div id="goods-main">
    <GoodsNav @componentName="componentName = $event"></GoodsNav>
    <component :is="componentName" @componentName="componentName = $event"></component>
  </div>
</template>

<script>
import GoodsNav from "../GoodsNav/GoodsNav.vue"
import GoodsTable from "../GoodsTable/GoodsTable.vue"
import GoodsPlus from "../GoodsPlus/GoodsPlus.vue"
import NewFlow from "../NewFlow/NewFlow.vue"

export default {
  name: 'GoodsMain',
  components:{
    GoodsNav,
    GoodsTable,
    GoodsPlus,
    NewFlow
  },
  data () {
    return {
      componentName:"GoodsTable"
    }
  }
}
</script>

<style lang="scss">



</style>