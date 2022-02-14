<template>
    <ul>
        <li class="card" v-for="(movie,index) in movies" :key='index'>
            {{}}
        </li>
    </ul>
</template>

<script>
export default {
    data(){
        return{
            movies: [],
        };
    },
    mounted(){
        axios.get().then((res) => {this.movies})
    }
}
</script>

<style scoped lang='scss'>

</style>