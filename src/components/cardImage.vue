<template>
  <div class="card-image">
    <div class="image is-4by3 img">
      <img :src="imgSrc" alt="Placeholder image" />
    </div>
    <div class="grid-columns-3 image-nav">
      <img
        v-for="path in imgPath"
        :src="path.src"
        alt="Placeholder image"
        :key="path.id"
        @click="showImg(path.src)"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "cardImage",
  props: ["img-path"],
  data() {
    return {
      imgSrc: this.imgPath[0].src,
    };
  },
  methods: {
    showImg(src) {
      this.imgSrc = src;
    },
  },
  watch: {
    imgPath: function (newPaths) {
      this.imgSrc = newPaths[0].src;
    },
  },
};
</script>

<style lang="css" scoped>
.image-nav img {
  width: 8em;
}
.image-nav img:hover {
  opacity: 0.5;
}
.grid-columns-3 {
  display: grid;
  grid-template-columns: 33.33333% 33.33333% 33.33333%;
}
</style>