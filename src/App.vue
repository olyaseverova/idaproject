<template>
  <div class="nav">
    <Form />
    <Products />
  </div>
</template>

<script>
import Form from "./components/Form.vue";
import Products from "./components/Products.vue";

export default {
  name: "App",
  components: {
    Form,
    Products,
  },
};
</script>
