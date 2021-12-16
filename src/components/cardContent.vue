<template>
  <div class="card-content">
    <p v-html="itemAbout"></p>
  </div>
</template>

<script>
export default {
  name: "cardContent",
  props: ["item-about"],
};
</script>

<style lang="scss" scoped>
</style>