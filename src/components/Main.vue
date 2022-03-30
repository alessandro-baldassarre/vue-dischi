<template>
  <main>
    <Albums />
  </main>
</template>

<script>
import Albums from "./Albums.vue";
export default {
  name: "IndexMain",
  
  components: {
    Albums,
    
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";


</style>
