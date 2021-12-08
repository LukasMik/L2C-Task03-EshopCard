<template>
  <div class="card-image">
    <div class="image is-4by3">
      <img :src="imgShow" alt="Placeholder image" />
    </div>
    <div class="grid-columns-3 image-nav">
      <img :src="imgPath1" alt="Placeholder image" @click="showImg1()"/>
      <img :src="imgPath2" alt="Placeholder image" @click="showImg2()"/>
      <img :src="imgPath3" alt="Placeholder image" @click="showImg3()"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "cardImage",
  props: ["imgPath1","imgPath2","imgPath3"],
  data() {
    return {
      imgShow: this.imgPath1,
    }
  },
  methods: {
    showImg1() { 
      this.imgShow = this.imgPath1
      return this.imgShow
       },
    showImg2() { 
      this.imgShow = this.imgPath2
      return this.imgShow
       },
    showImg3() { 
      this.imgShow = this.imgPath3
      return this.imgShow
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