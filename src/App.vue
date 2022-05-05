<template>
  <div id="app">
    
    <div class="container bg-secondary vh-100">
      <div class="row">
        <div class="col-2 bg-primary" v-for="album in albums" :key="album.title">
          {{album.title}}
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import axios from "axios";

export default {
  name: 'App',
  components: {
    
  },
  data() {
    return {
      api_url: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: null,
      error: null,
    };
  },
  methods: {
    callApi() {
      axios
        .get(this.api_url)
        .then((response) => {
          //console.log(response);
          this.albums = response.data.response;
          console.log(this.albums);
        })
        .catch((error) => {
          console.error();
          error;
          this.error = `Sorry, there is a problem! ${error}`;
        });
    },
  },
  mounted() {
    this.callApi();
  },
}

</script>

<style lang="scss">
  
  @import '@/assets/scss/style.scss';

</style>
