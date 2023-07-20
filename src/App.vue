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
      store: store,
    };
  },
  created() {
    axios
      .get("")
      .then(response => {
        console.log(response);
      });
  },
};
</script>

<template>
 <headerComponent/>
  
</template>

<style lang="scss" scoped>
@use "assets/scss/main";
body{
  margin: 0;
}
</style>
