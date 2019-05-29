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
  data () {
    return {
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
        ]
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