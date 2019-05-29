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
        <tr v-for="(item, index) of goodsAll" :key="item.id">
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
  props:["goodsAll"],
  data() {
    return {
        
    };
  }
};
</script>

<style lang="scss">
</style>