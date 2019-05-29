<template>
  <div id="goods-main">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="menu-icon" @click="show()">
        <div class="menu-icon-item"></div>
        <div class="menu-icon-item"></div>
        <div class="menu-icon-item"></div>
      </div>
      <a class="navbar-brand" href="#">Склад</a>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item active">
            <a class="nav-link" @click="changeName('GoodsTable')">
              Материалы
              <span class="sr-only">(current)</span>
            </a>
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
  name: "GoodsNav",
  props:["showMenu"],
  data() {
    return {};
  },
  methods: {
    changeName(value) {
      this.$emit("componentName", value);
    },
    show(){
      this.showMenu = !this.showMenu
      this.$emit("showMenu", this.showMenu);
    }
  }
};
</script>

<style lang="scss">
  .menu-icon-item{
    width: 35px;
    height: 5px;
    background-color: black;
    margin: 6px 20px 6px 0;
  }
</style>