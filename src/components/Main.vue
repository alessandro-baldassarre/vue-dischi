<template>
  <main>
    <Albums @sendGenereList="createGenreList" />
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
  methods: {
    createGenreList(genreList) {
      this.genreList = genreList;
      this.$emit('sendGenereList',this.genreList);  
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";
</style>
