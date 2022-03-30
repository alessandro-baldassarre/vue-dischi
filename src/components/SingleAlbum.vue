<template>
  <div class="single-album p-4 rounded text-center">
    <img
      :src="imgUrl"
      class="img-fluid"
      :alt="title + 'cover'"
    />
    <div>
      <h5 class="my-3 text-white text-uppercase">
        {{title}}
      </h5>
      <p class="text-secondary m-0 p-0">
        {{author}}
      </p>
       <p class="text-secondary m-0 p-0">
        {{year}}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleAlbum",
  props: {
    imgUrl: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";

div.single-album {
  width: 180px;
  background-color: $bgLightDark;
  img{
    width: 170px;
    height: 140px;
  }
  h5{
    font-size: .7rem;
  }
  p{
    font-size: .6rem;
  }
}
</style>
