<template>
    <ul>
        <li class="card" v-for="(movie,index) in movies" :key='index'>
            {{movie.title}}
    <span>{{movie.vote_average}}</span>
    <p>{{movie.original_title}}</p>
    <p>{{movie.original_language}}</p>
        </li>
    </ul>
</template>

<script>
    import axios from 'axios';

export default {
    data(){
        return{
            movies: [],
            api: 'c15aa4b26195705c0e005c100069298c',
        };
    },
    methods: {
        callApi (query){
                    axios.get(`https://api.themoviedb.org/3/search/movie?query=${query}&api_key=${this.api}`)
                    .then((res) => {
                    this.movies = res.data.results;
                })
            }
    },
    mounted() { 
        this.callApi('ciao');
    },
    
}
</script>

<style scoped lang='scss'>

</style>