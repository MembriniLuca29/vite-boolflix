<script>
import { store } from '../store.js';

export default {
    name:"mainComponent",
  data() {
    
    return {
      store
    };
  },
}
</script>

<template>
    <div class="main-container">
    <div class="film-card-container" 
    v-for="(movie, i) in store.movies" :key="i" >
    <ul>
      <li >
        <ol>
          <li>{{ movie.title }}</li>
          <li>{{ movie.original_title}}</li>
          <li>{{movie.original_language}}</li>
          <li>{{ movie.vote_average}}</li>
        </ol>
      </li>
    </ul>
</div>
</div>
</template>

<style lang="scss" scoped>

.main-container{
    width: 100%;
    background-color: black;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}
.film-card-container{
background-color: white;
width: 22%;
display: flex;
margin-top: 20px;
margin-bottom: 10px;
}
</style>