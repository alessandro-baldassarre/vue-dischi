<template>
  <header>
    <img src="@/assets/img/logo.png" alt="spotify logo">
  </header>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";

header{
  height: 50px;
  background-color: $bgLightDark;
  img{
    height: 100%;
  }
}

</style>
