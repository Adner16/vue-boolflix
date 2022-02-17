<template>
    <div>
        <div class="container">
            <div class="card" v-for="(item,index) in items" :key='index'>
                <img  class='poster' v-if="item.poster_path" :src="`https://image.tmdb.org/t/p/w342${item.poster_path}`" alt="">
                <div class="info">
                    <p v-if="item.title">{{item.title}}</p>
                    <p v-else>{{item.name}}</p>
                    <p>{{item.vote_average}}</p> 
                    <p><font-awesome-icon icon ="fas fa-star" v-for="i in createVote(item.vote_average)" :key="i"></font-awesome-icon><font-awesome-icon icon ="far fa-star" v-for="i in (5 - createVote(item.vote_average))" :key="i"></font-awesome-icon></p>
                    <p v-if="item.title">{{item.original_title}}</p>
                    <p v-else>{{item.original_name}}</p>
                    <img id='lang' v-if='item.original_language == "en" || item.original_language == "it"' :src="getImg(item.original_language)" alt="">    
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    
export default {
    name: 'Card',
    props:  ['items','moviePost', 'tvPost'],

    methods: {
        getImg(language){
                return require(`../../img/${language}.png`)
        }, 
        createVote(vote){
            return Math.ceil(vote / 2);
        },
        
        }
}
</script>

<style scoped lang='scss'>
    
    .container{
        display: flex;
        flex-wrap: wrap;
        width: 1300px;
        margin: auto;
        .card{
            border: 2px solid white;
            margin: 30px;

            .poster{

            }
            .info{
                display: none;
            }
            #lang{
            width: 30px;
        }
    }

    }
    
</style>