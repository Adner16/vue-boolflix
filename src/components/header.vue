<template>
    <div>
        <input v-model="this.movie" type="text">
        <button @click="findMovie">VAI</button>
    </div>
    
</template>

<script>
export default {
    data(){
        return{
            movie: '',
        }
    }
    // methods:{
            
    //     }
    }

</script>

<style>

</style>