<template>
  <div id="goods-main">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Склад</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" @click="changeName('GoodsTable')">Материалы <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" @click="changeName('GoodsPlus')">Поступления</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Анализ</a>
      </li>
    </ul>
  </div>
</nav>

  </div>
</template>

<script>
export default {
  name: 'GoodsNav',
  data () {
    return {
     
    }
  },
  methods:{
      changeName(value){
          this.$emit("componentName", value)
      }
  }
}
</script>

<style lang="scss">


</style>