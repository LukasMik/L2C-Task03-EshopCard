<template>
  <div class="specialPrice" v-show="this.salePerc > 0">
    <p>
      <span class="oldPrice">{{ itemPrice }} $</span>
      <br />
      <span class="sale">-{{ salePerc }} %</span>
    </p>
  </div>
</template>

<script>
export default {
  name: "speacialPrice",
  props: ["item-price", "sale-perc"],
};
</script>

<style lang="css" scoped>
.specialPrice {
  position: relative;
  top: -40rem;
  left: 22rem;
  z-index: 1;
  width: 6em;
  height: 6em;
  background-color: black;
  border-radius: 50%;
  text-align: center;
  color: #fff;
  font-weight: 600;
  letter-spacing: 1px;
}

.oldPrice {
  text-decoration: line-through;
}

.sale {
  font-size: 1.5em;
}

p {
  position: relative;
  top: 1em;
}
</style>