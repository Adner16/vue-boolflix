<template>
    <div>
        <Header @query= 'startSearch'/>
        <h2>movie</h2>
        <Card :items='movies'/>
        <h2>show</h2>
        <Card :items='shows'  />
        <Card :moviePost='posterMovie'/>
        <Card :tvPost='posterTv'/>
    </div>
    
</template>

<script>
    import axios from 'axios';
    import Card from './Card';
    import Header from './Header'

export default {
    components: {
        Card,
        Header
    },
    data(){
        return{
            search: '',
            posterMovie: '',
            posterTv: '',
            shows: [],
            movies: [],
            api: 'c15aa4b26195705c0e005c100069298c',
        };
    },
    methods: {
        callApi (){
                    axios.get(`https://api.themoviedb.org/3/search/movie?query=${this.search}&api_key=${this.api}`)
                    .then((res) => {
                        this.movies = res.data.results;
                    });
                    axios.get(`https://api.themoviedb.org/3/search/tv?query=${this.search}&api_key=${this.api}`)
                    .then((res) => {
                        this.shows = res.data.results;
                    });
            },
            startSearch(value){
                this.search = value;
                this.callApi();
            }
        
           
    },
}
</script>

<style scoped lang='scss'>
    
</style>

// https://api.themoviedb.org/3/search/movie?query=${this.search}&api_key=c15aa4b26195705c0e005c100069298c