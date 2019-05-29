<template>
  <div id="goods-plus">
    <div class="btn btn-primary plus" @click="newFlow()">+добавить</div>
    <table class="table table-striped table-plus">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Наименование документа</th>
          <th scope="col">Поставщик</th>
          <th scope="col">Дата поступления</th>
          <th scope="col">Сумма общая</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) of documents" :key="item.id">
          <th scope="row">{{index+1}}</th>
          <td>{{item.name}}</td>
          <td>{{item.sailer}}</td>
          <td>{{item.date}}</td>
          <td>{{item.sum}} руб.</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'GoodsPlus',
  props:["documents"],
  data () {
    return {
        
    }
  },
  methods:{
      newFlow(){
          var value = ""
          this.$emit("componentName", "NewFlow")
      }
  }
}
</script>

<style lang="scss">
    .plus{
        position: absolute;
        margin: -50px 20px 20px 0;
        right: 0;
    }
    .table-plus{
        margin: 60px 0 0 0;
    }

</style>