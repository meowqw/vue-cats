<template>
  <div>
    <div class="v-catalog-item">
      <h1>{{ title }}</h1>
      <img
        class="v-catalog-item__image"
        :src="require('../../assets/images/' + product_data.image)"
        alt="img"
      />
      <p class="v-catalog-item__name">{{ product_data.name }}</p>
      <p class="v-catalog-item__price">Price {{ product_data.price }}</p>
      <button class="v-catalog-item__add_to_cart btn" @click="addToCart">
        Add to card
      </button>
    </div>
  </div>
</template>

<script>

export default {
  name: "v-catalog-item",
  components: {},
  props: {
    product_data: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {
      title: "Catalog item",
    };
  },
  computed: {},
  methods: {
    addToCart() {
      this.$emit("addToCart", this.product_data);
    },
  },
  watch: {},
  mounted() {
    console.log("comp v-catalog-item");
  },
};
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: $padding * 2;
  margin-bottom: $margin * 2;
  &__image {
    width: 100px;
    height: 100px;
  }
}
</style>