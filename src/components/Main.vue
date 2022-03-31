<template>
  <main>
    <Albums @sendGenereList="createGenreList" :option="option" :generetedArrayFinded="generetedArrayFinded"/>
  </main>
</template>

<script>
import Albums from "./Albums.vue";
export default {
  name: "IndexMain",

  components: {
    Albums,
  },
  data: function () {
    return {
      genreList: null,
    };
  },
  props: {
    option: String,
    generetedArrayFinded: Array,
  },
  methods: {
    createGenreList(genreList, albumsList) {
      this.genreList = genreList;
      this.$emit('sendGenereList',this.genreList, albumsList);  
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";
</style>
