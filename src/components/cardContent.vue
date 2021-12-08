<template>
  <div class="card-content">
    <p>
      {{ itemAbout }}
    </p>
  </div>
</template>

<script>
export default {
  name: "cardContent",
  props: ["itemAbout"]
};
</script>

<style lang="scss" scoped>
</style>