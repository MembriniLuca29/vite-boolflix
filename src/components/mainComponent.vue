<script>
import { store } from '../store.js';

export default {
    name:"mainComponent",
  data() {
    
    return {
      store
    };
  },
  methods: {
     getFlag(lang) {
        if(lang == 'it'){
            return 'https://flagicons.lipis.dev/flags/4x3/it.svg';
        }
        else if (lang == 'ja'){
            return 'https://flagicons.lipis.dev/flags/4x3/jp.svg';
        }
        else if (lang == 'en'){
            return 'https://flagicons.lipis.dev/flags/4x3/us.svg';
        }
        else if (lang == 'es'){
            return 'https://flagicons.lipis.dev/flags/4x3/es.svg';
        }
        else {
            return 'https://flagicons.lipis.dev/flags/4x3/xx.svg';
        }
  },
  getCover(poster){
     const defaultImageUrl = 'https://www.prolococisanobg.it/wp-content/uploads/2017/10/Non-disponibile-_04.jpg'; 
        if (!poster || poster === 'null') {
            return defaultImageUrl;
        } 
        else{
            return 'https://image.tmdb.org/t/p/w342/' + poster;
        }
    }
}
}
</script>

<template>
    <div class="main-container">
      <div class="title">
        <h2>Film</h2>
      </div>
      <div
        class="film-card-container"
        v-for="(movie, i) in store.movies"
        :key="i"
      >
          <img :src="getCover(movie.poster_path)" :alt="movie.original_name" class="movie-image">
          <ul class="movie-details" >
            <li>{{ movie.title }}</li>
            <li>{{ movie.original_title }}</li>
            <li>
              <img :src="getFlag(movie.original_language)" :alt="movie.original_language" class="language-flag">
            </li>
            <li>{{ movie.vote_average }}</li>
          </ul>
      </div>
      <div class="title">
        <h2>Serie</h2>
      </div>
      <div
        class="film-card-container"
        v-for="(serie, i) in store.series"
        :key="i"
      >
          <img :src="getCover(serie.poster_path)" :alt="serie.original_name" class="movie-image">
          <ul class="movie-details" >
            <li>{{ serie.name }}</li>
            <li>{{ serie.original_name }}</li>
            <li>
              <img :src="getFlag(serie.original_language)" :alt="serie.original_language" class="language-flag">
            </li>
            <li>{{ serie.vote_average }}</li>
          </ul>
      </div>
    </div>
  </template>

<style lang="scss" scoped>

.main-container{
    width: 80%;
    background-color: white;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    margin: 0 auto;
}
.title{
    width: 100%;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    font-size: 3rem;
    font-weight: bold;
    color: yellow;
    border: 10px solid white;
    h2{
        background-color: green;
        width: 20%;
        text-align: center;
    }
}
.film-card-container{
background-color: black;
color: white;
width: 330px;
height: 500px;
display: flex;
margin-top: 20px;
margin-bottom: 10px;
position: relative;
ul{
    list-style: none;
    padding: 0;
    position: absolute;
    width: 100%;
    padding: 20px 0;
}
li{
    list-style: none;
    font-size: 2.0rem;
    text-align: center;
    img{
        height: 50px;
    }
}
}
.movie-details{
display: none;
}

.movie-image{
    object-fit: cover;
    object-position: center;
    max-width: 330px;
}
.film-card-container:hover{
   .movie-image{
    opacity: 0.3;
   }
   .movie-details{
    display: block;
   }
}
</style>