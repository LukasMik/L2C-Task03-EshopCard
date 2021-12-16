<template>
  <p>
    <span class="stock">In stock: </span>
    <span class="amount">({{ itemStock }} pcs)</span>
    <br />
    <span class="lastPieces" v-if="this.itemStock <= 5 && this.itemStock > 0"
      >Last {{ itemStock }} pieces!</span
    >
    <span class="sold" v-if="this.itemStock === 0">Sold!</span>
  </p>
</template>

<script>
export default {
  name: "cardStock",
  props: ["item-stock"],
};
</script>

<style lang="css" scoped>
p {
  margin-left: 6.5em;
}

.stock {
  color: #bada55;
  font-weight: 700;
}

.lastPieces,
.sold {
  font-weight: 700;
  color: tomato;
}

.sold {
  font-size: 1.5em;
}
</style>