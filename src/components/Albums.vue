<template>
  <div>
    <div v-if="albumsList" class="container-fluid p-5">
      <div v-if="(option != '')" class="row px-5 gy-3 p-5">
        <div
          v-for="(album, index) in generetedArrayFinded"
          :key="index"
          class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 d-flex flex-shrink-1 justify-content-center"
        >
          <SingleAlbum
            :imgUrl="album.poster"
            :title="album.title"
            :author="album.author"
            :year="album.year"
          />
        </div>
        
      </div>
       <div v-else class="row px-5 gy-3 flex-wrap p-5">
        <div
          v-for="(album, index) in albumsList"
          :key="index"
          class="col-12 col-sm-6 col-md-4 col-lg-3 col-xl-2 d-flex flex-shrink-1 justify-content-center"
        >
          <SingleAlbum
            :imgUrl="album.poster"
            :title="album.title"
            :author="album.author"
            :year="album.year"
          />
        </div>
        
      </div>
    </div>

    <div v-else>
      <Loader />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SingleAlbum from "./SingleAlbum.vue";
import Loader from "./Loader.vue";
export default {
  name: "MainAlbums",
  components: {
    SingleAlbum,
    Loader,
  },
  data: function () {
    return {
      albumsList: null,
      errors: null,
      genereList: [],
    };
  },
  props: {
    option: String,
    generetedArrayFinded: Array,
  },
  methods: {
    getAlbumsApi() {
      axios
        .get(`https://flynn.boolean.careers/exercises/api/array/music`)
        .then((response) => {
          this.albumsList = response.data.response;   
          this.sendGenereList();
        })
        .catch((e) => {
          this.errors.push(e);
        });
  
     
    },
    sendGenereList() {
      this.albumsList.forEach(element => {
        if(!this.genereList.includes(element.genre)){
            this.genereList.push(element.genre);
        }
        
      });
      this.$emit('sendGenereList',this.genereList, this.albumsList);     
    },
  },
  created() {
    setTimeout(this.getAlbumsApi, 3000);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "@/assets/scss/partials/_variables";
</style>
