<template>
  <div id="new-flow">
    <h1>Новое поступление материалов</h1>
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Поставщик</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="SailerName"
      >
    </div>

    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">дата поступления</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="SaleDate"
      >
    </div>
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">номер документа</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="DocNum"
      >
    </div>

    <div class="btn btn-primary" @click="showNewForm = !showNewForm">+новая строка</div>

    <div class="new-string" v-show="showNewForm">
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">наименование материала</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="GoodName"
      >
    </div>
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">единица измерения</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="UoM"
      >
    </div>
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Количество</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="quantity"
      >
    </div>
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1">Цена за ед.изм.</span>
      </div>
      <input
        type="text"
        class="form-control"
        placeholder="Имя пользователя"
        aria-label="Имя пользователя"
        aria-describedby="basic-addon1"
        v-model="price"
      >
    </div>
    <div class="btn btn-primary" @click="NewString()">добавить строку</div>
    </div>

    

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

    <div class="btn btn-primary" @click="NewDoc()">сохранить</div>
  </div>
</template>

<script>
export default {
  name: "NewFlow",
  props: ["documents","goodsAll"],
  data() {
    return {
      goods:[
        ],
        showNewForm: false,
        GoodName: "",
        UoM: "",
        price: "",
        quantity: "",
        SailerName: "",
        SaleDate: "",
        DocNum: ""
    };
  },
  methods:{
    NewString(){
      var Str = {}
      if(this.goods[this.goods.length-1]=== undefined){
        Str.id = 0
      } else {
        Str.id = this.goods[this.goods.length-1].id + 1
      }
      Str.name = this.GoodName
      Str.UoM = this.UoM
      Str.sum = Number(this.price)*Number(this.quantity)
      Str.quantity = this.quantity
      Str.price = this.price
      this.goods.push(Str)
    },
    NewDoc(){
      var doc = {}
      var sum = 0
      doc.id = this.documents[this.documents.length-1].id + 1
      doc.name = this.DocNum
      doc.sailer = this.SailerName
      doc.date = this.SaleDate
      for(var i=0; i<this.goods.length; i++){
        sum += this.goods[i].sum
        for(var n=0; n<this.goodsAll.length; n++){
          if(this.goodsAll[n].name === this.goods[i].name){
            alert(this.goods[i].quantity)
            this.goodsAll[n].sum = Number(this.goodsAll[n].sum) + Number(this.goods[i].quantity) 
          }
        }
      }
      doc.sum = sum
      doc.goods = this.goods
      this.documents.push(doc)
      this.$emit("documents", this.documents)
      this.$emit("goodsAll", this.goodsAll)
    }
  }
};
</script>

<style lang="scss">
</style>