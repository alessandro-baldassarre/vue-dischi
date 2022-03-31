<template>
  <header class="container-fluid ps-2 pe-5">
    <div class="row">
      <div class="col-12 d-flex justify-content-between align-items-center">
        <div class="logo">
          <img src="@/assets/img/logo.png" alt="spotify logo" />
        </div>
        <div class="select-bar px-5">
          <select name="select-album" id="select-album">
            <option selected>Scegli Genere</option>
            <option
              v-for="(element, index) in genereList"
              :key="index"
              :value="element.genre"
            >
              {{ element }}
            </option>
          </select>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "IndexHeader",

  props: {
    genereList: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";

header {
  height: 50px;
  background-color: $bgLightDark;
  div.logo {
    img {
      width: 70px;
    }
    height: 100%;
  }
}
</style>
