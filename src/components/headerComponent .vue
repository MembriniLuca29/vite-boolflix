<script>
import { store } from '../store.js';

export default {
    name:"headerComponent",
  data() {
    return {
      store
    };
  },
  
  };
</script>

<template>
  <div class="header-container">
    <div class="logo"><h1>BOOLFLIX</h1></div>
<input type="text" placeholder="ricerca..." v-model="store.searchText">
<button type="button" @click="$emit('performSearch')">cerca</button>
  </div>
</template>

<style lang="scss" scoped>
.header-container{
    display: flex;
    align-items: center;
    
    background-color: black;
    height: 200px;
    width: 100%;
    .logo{
        color: red;
        width: 40%;
        padding-left: 30px;
        font-size: 2rem;
    }
    input{
        padding: 10px 30px 10px 10px;
        font-size: 1.5rem;
        margin-right: 10px;
    }
    button{
        padding: 23px;
        background-color: gray;
    }
    button:hover{
        background-color: lightblue;
    }
}
</style>