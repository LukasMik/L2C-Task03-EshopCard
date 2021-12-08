<template>
  <header class="card-header">
    <p class="card-header-title">{{ itemName }}</p>
    <img src="../assets/img/arrow.png" alt="other" @click="changeSelected()">
  </header>
</template>

<script>
export default {
  name: "cardHeader",
  props: ["itemName","productLength"],
  data() {
    return {
      selected: 0,
    }
  },
  methods: {
    changeSelected() {
      if (this.selected >= 0 && this.selected < this.productLength - 1){
        this.selected = this.selected + 1
      }
      else if (this.selected === this.productLength - 1){
        this.selected = 0
      }
      this.$emit("changeSelected", this.selected)
      console.log(this.selected)
    },
  },
};
</script>

<style lang="css" scoped>
.card-header{
  font-size: 1.5em;
}
img {
  width: 1.5em;
  height: 1.5em;
  margin: 0.5em 1em;
}
img:hover{
  opacity: 0.5;
  cursor: pointer;
}
</style>