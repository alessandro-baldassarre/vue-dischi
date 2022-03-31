<template>
  <div id="app">
    <Header :genereList = "genreList" :albumList="albumsListFind"  @sendOption="sendOption" />

    <Main @sendGenereList="createGenreList" :option="option" :generetedArrayFinded="generetedArrayFinded"/>
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
      albumsListFind: null,
      option: "",
      generetedArrayFinded : [],
    };
  },
  methods: {
    createGenreList(genreList, albumsList) {
      this.genreList = genreList;
      this.albumsListFind = albumsList;
    },
    sendOption(option, array) {
      this.option = option;
      this.generetedArrayFinded = array;
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/scss/style.scss";
</style>
