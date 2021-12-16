<template>
  <div class="card-content">
    <div class="display-flex container">
      <p class="oldPrice" v-if="this.salePerc > 0">{{ itemPrice }} $</p>
      <p class="sale" v-if="this.salePerc > 0">-{{ salePerc }} %</p>
    </div>
    <p class="price">{{ priceCount() }} $</p>
  </div>
</template>

<script>
export default {
  name: "cardPrice",
  props: ["item-price", "sale-perc"],

  methods: {
    priceCount() {
      return this.itemPrice * ((100 - this.salePerc) / 100);
    },
  },
};
</script>

<style lang="css" scoped>
.card-content {
  padding-top: 0;
  letter-spacing: 1px;
}

.oldPrice {
  text-decoration: line-through;
}

.display-flex {
  display: flex;
}

.container {
  font-weight: 600;
}

.sale {
  margin-left: 1em;
}

.price {
  font-size: 1.7em;
  color: #bada55;
  font-weight: 700;
  line-height: 1em;
}
</style>