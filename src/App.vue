<template>
  <div id="app">
    <Header :genereList = "genreList"/>

    <Main @sendGenereList="createGenreList"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";

export default {
  name: "App",
  components: {
    Header,
    Main,
  },
  data: function () {
    return {
      genreList: null,
    };
  },
  methods: {
    createGenreList(genreList) {
      this.genreList = genreList;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
