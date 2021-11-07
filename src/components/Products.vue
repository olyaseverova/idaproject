<template>
  <div class="products">
    <ul class="products-list list">
      <li
        class="products-list__item"
        v-for="product in products"
        :key="product.id"
      >
        <img
          class="products-list__img"
          :src="product.src"
          width="332"
          height="200"
          alt="Фотография продукта"
        />
        <div class="products-list__text">
          <h3 class="products-list__name">{{ product.name }}</h3>
          <p class="products-list__description">{{ product.description }}</p>
          <h2 class="products-list__price">{{ product.price }}</h2>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Products",

  data() {
    return {
      products: [
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 0,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 1,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 2,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 3,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 4,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 5,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 6,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 7,
        },
        {
          src: require("@/img/product.png"),
          name: "Наименование товара",
          description:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
          id: 8,
        },
      ],
    };
  },
};
</script>