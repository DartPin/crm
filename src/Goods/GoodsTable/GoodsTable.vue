<template>
  <div id="goods-table">
    <table class="table table-striped">
      <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Наименование</th>
          <th scope="col">Единица измерения</th>
          <th scope="col">Количество на складе</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) of goods" :key="item.id">
          <th scope="row">{{index+1}}</th>
          <td>{{item.name}}</td>
          <td>{{item.UoM}}</td>
          <td>{{item.sum}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "GoodsTable",
  data() {
    return {
        goods:[
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
        ]
    };
  }
};
</script>

<style lang="scss">
</style>