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
      >
    </div>

    <div class="btn btn-primary">+новая строка</div>

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
      >
    </div>

    <div class="btn btn-primary">добавить</div>

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
  name: "NewFlow",
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