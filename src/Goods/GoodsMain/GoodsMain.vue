<template>
  <div id="goods-main">
    <Menu v-show="showMenu"></Menu>
    <GoodsNav @componentName="componentName = $event" :showMenu="showMenu" @showMenu="showMenu = $event"></GoodsNav>
    <component :is="componentName" @componentName="componentName = $event" :documents="documents" @documents="documents = $event" :goodsAll="goodsAll"></component>
  </div>
</template>

<script>
import GoodsNav from "../GoodsNav/GoodsNav.vue"
import GoodsTable from "../GoodsTable/GoodsTable.vue"
import GoodsPlus from "../GoodsPlus/GoodsPlus.vue"
import NewFlow from "../NewFlow/NewFlow.vue"
import Menu from "../../Menu/Menu.vue"

export default {
  name: 'GoodsMain',
  components:{
    GoodsNav,
    GoodsTable,
    GoodsPlus,
    NewFlow,
    Menu
  },
  data () {
    return {
      componentName:"GoodsTable",
      documents:[
            {
                id: 1,
                name: "нак. №351",
                sailer: "Продавец баннеров",
                date: "31 мая",
                sum: 23199.01
            },
            {
                id: 2,
                name: "нак. №353",
                sailer: "Продавец пленки",
                date: "31 мая",
                sum: 18546.09
            },
            {
                id: 3,
                name: "нак. №355",
                sailer: "Продавец баннеров",
                date: "31 мая",
                sum: 56324.00
            },
            {
                id: 4,
                name: "нак. №356",
                sailer: "Продавец пленки",
                date: "31 мая",
                sum: 16542.41
            },
        ],
        goodsAll:[
            {
                id: 1,
                name: "баннер 330",
                UoM: "м2",
                sum: 300
            },
            {
                id: 2,
                name: "баннер 550",
                UoM: "м2",
                sum: 150
            },
            {
                id: 3,
                name: "баннер 440",
                UoM: "м2",
                sum: 200
            }
        ],
        showMenu: false
    }
  }
}
</script>

<style lang="scss">



</style>