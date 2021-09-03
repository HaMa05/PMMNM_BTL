<template>
  <b-carousel controls img-width="1859" img-height="100%" :interval="3000">
    <b-carousel-slide
      v-for="item in slide"
      :key="item.id"
      :img-src="`http://127.0.0.1:8000/storage/uploads/${item.image}`"
      :caption="item.name"
      :text-html="item.description"
      :style="[imageObject]"
    ></b-carousel-slide>
  </b-carousel>
</template>
<script>
export default {
  data() {
    return {
      slide: [],
      imageObject: {
        height: "100%",
        "object-fit": "cover"
      }
    };
  },
  created() {
    this.$axios.get("/slide").then(res => {
      this.slide = res.data;
      console.log(this.slide);
    });
  }
};
</script>

<style lang="scss">
.carousel-inner {
  height: 550px !important;
}

.carousel-item img {
  height: 100%;
  object-fit: contain;
}

img {
  height: 100%;
  object-fit: cover;
}
</style>
