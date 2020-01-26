<template>
    <section class='searchbox-wrap'>
        <input type="text" placeholder='Search for a movie' v-model='searchTerm' class='searchbox' @keypress.enter='searchMovies()'/>
        <button class='searchButton' @click='searchMovies()'>Search</button>
        <Results :results="this.films"/>
    </section>
</template>

<script>
import axios from 'axios';
import Results from './Results';
export default {
  name: 'Search',
  components: {
      Results,
  },
  data(){
    return {searchTerm: this.searchTerm, films:[], error: ''}
  },
  methods:{
    searchMovies(){
    axios.get('http://www.omdbapi.com/?s='+this.searchTerm+'&apikey=XXXX&page=1&type=movie&Content-Type=application/json')
    .then(response => {
      this.films = response.data.Search
      console.log(this.films);
    })
    .catch(error => {
      this.error = error;
      console.log(error)
    })
    },
  },
}
</script>

<style scoped>

.searchbox {
	display: inline-block;
	width: 90%;
	padding: 15px;

	border: none;
	outline: none;
	background: none;

	background-color: #EEE;
	border-radius: 8px;

	color: #53565A;
	font-size: 20px;
	font-weight: 300;

	transition: 0.4s ease-out;
}

.searchButton {
    transition:  0.4s ease-out;
    border-radius: 8px;
    padding: 15px;
    display: inline-block;
    margin-left: 10px;
}

.searchbox:focus {
	box-shadow: 0px 0px 8px 3px #4484C4;
}
</style>
