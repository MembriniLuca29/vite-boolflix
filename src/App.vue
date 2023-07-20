<script>
import headerComponent from './components/headerComponent .vue';
import mainComponent from './components/mainComponent.vue';
import footerComponent from './components/footerComponent.vue'
import axios from 'axios';
import { store } from './store.js';

export default {
  name: "app",
  components: {
    headerComponent,
    mainComponent,
    footerComponent,
  },
  data() {
    return {
      store
    };
  },
  methods: {
    search() {
        console.log(this.store.searchText)

        axios
          .get("https://api.themoviedb.org/3/search/movie", {
            params: {
              api_key: '0d5f1072b59944dbc0378fbd0aac6382',
              query: this.store.searchText
            }
          })
          .then(res => {
            this.store.movies = res.data.results;
            console.log(res.data);
        });

        axios
          .get("https://api.themoviedb.org/3/search/tv", {
            params: {
              api_key: '0d5f1072b59944dbc0378fbd0aac6382',
              query: this.store.searchText
            }
          })
          .then(res => {
            this.store.series = res.data.results;
            console.log(res.data);
        });
  }
  },
};
</script>

<template>
 <headerComponent @performSearch="search()"/>
 <mainComponent/>
  
</template>

<style lang="scss" scoped>
@use "assets/scss/main";
body{
  margin: 0;
}

</style>
