<template>
  <div class="specialPrice" v-if="this.salePerc > 0">
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
  props: ["itemPrice", "salePerc"]
};
</script>

<style lang="css" scoped>
.specialPrice {
  position: relative;
  background-color: black;
  border-radius: 50%;
  width: 6em;
  height: 6em;
  text-align: center;
  top: 30em;
  left: 22em;
  color: #fff;
  font-weight: 600;
  letter-spacing: 1px;
  z-index: 1;
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