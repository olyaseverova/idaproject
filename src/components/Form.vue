<template>
  <div class="form">
    <h1 class="headline">Добавление товара</h1>
    <form
      class="addProduct"
      method="post"
      action=""
      enctype="multipart/form-data"
    >
      <label class="addProduct__label">
        <p class="addProduct__text required-field">Наименование товара</p>
        <input
          required
          type="text"
          class="addProduct__input name-field"
          pattern="^[А-Яа-яЁё\s-]+$"
          placeholder="Введите наименование товара"
          @keyup="checkFields"
        />
      </label>
      <label class="addProduct__label">
        <p class="addProduct__text">Описание товара</p>
        <textarea
          type="text"
          class="addProduct__input addProduct__textarea"
          placeholder="Введите описание товара"
          @click="checkDescription"
        />
      </label>
      <label class="addProduct__label">
        <p class="addProduct__text required-field">
          Ссылка на изображение товара
        </p>
        <input
          required
          type="text"
          class="addProduct__input link-field"
          placeholder="Введите ссылку"
          @click="checkDescription"
          @keyup="checkFields"
        />
      </label>
      <label class="addProduct__label">
        <p class="addProduct__text required-field">Цена товара</p>
        <input
          required
          type="text"
          class="addProduct__input price-field"
          placeholder="Введите цену"
          pattern="((\d{1,})(\s{1,})?){1,}"
          @keyup="checkFields"
          @click="checkDescription"
        />
      </label>
      <button class="addProduct__button" type="submit" disabled>
        Добавить товар
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Form",

  methods: {
    checkFields: function (event) {
      var name = document.querySelector(".name-field");
      var link = document.querySelector(".link-field");
      var price = document.querySelector(".price-field");
      var button = document.querySelector(".addProduct__button");
      const regex = new RegExp(event.target.pattern);

      if (event.target.classList.contains("price-field")) {
        let v = event.target.value;
        v = Intl.NumberFormat("ru-RU").format(parseInt(v.replace(/\s+/g, "")));
        event.target.value = v;
      }

      if (
        event.target.value.search(regex) !== 0 ||
        event.target.textLength === 0
      ) {
        event.target.classList.add("invalid");
      } else {
        event.target.classList.remove("invalid");
      }

      if (
        !event.target.classList.contains("invalid") &&
        !name.classList.contains("invalid") &&
        !link.classList.contains("invalid") &&
        !price.classList.contains("invalid") &&
        event.target.textLength > 0 &&
        name.textLength > 0 &&
        link.textLength > 0 &&
        price.textLength > 0
      ) {
        button.removeAttribute("disabled", "disabled");
      } else {
        button.setAttribute("disabled", "disabled");
      }
    },

    checkDescription: function (event) {
      var name = document.querySelector(".name-field");
      var link = document.querySelector(".link-field");
      const nameRegex = new RegExp(name.pattern);
      if (name.textLength === 0 || name.value.search(nameRegex) !== 0) {
        name.classList.add("invalid");
      }

      if (
        event.target.classList.contains("price-field") &&
        link.textLength === 0
      ) {
        link.classList.add("invalid");
      }
    },
  },
};
</script>
