<template>
    <div>
        <h1>BOOLFLIX</h1>
        <div>
            <input v-model="movie" type="text">
            <button @click="search">VAI</button>
        </div>
        
    </div>
    
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            movie: '',
        }
    },
    methods:{
            search(){
                this.$emit('query', this.movie);
            }
        }
    }

</script>

<style scoped lang='scss'>
    div{
        height: 60px;
        background-color: black;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: 10px;
            h1{
                color: red;
                font-size: 30px
            }
    }
</style>