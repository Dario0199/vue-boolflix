<template>
    <div class="cards">
         <ul>
            <div class="cover-img">
                <li>
                    <img :src="`https://image.tmdb.org/t/p/w342${image}`" :alt="first_title">
                </li>
            
                <div class="info">
                    <li>
                        <span>Titolo:</span> 
                        {{ first_title }}
                    </li>
                    <li>
                        <span>Titolo originale:</span> 
                        {{ second_title }}
                    </li>
                    <li>
                        <span>Lingua:</span>
                        <img class="flag" v-if="flags.includes(language)" :src="require(`../assets/${language}.png`)" :alt="language"> 
                        <span v-else>{{ language }}</span>
                    </li>
                    <li>
                        <span>Voto:</span>
                        <span class="star" v-for="(star, index) in Math.ceil(vote / 2)" :key="`star-${index}`">
                            <i class="fas fa-star"></i>
                        </span>
                    </li>
                    <li>
                        <span>Descrizione:</span> 
                        {{ description }}
                    </li>
                </div>
            </div>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        image: String,
        first_title: String,
        second_title: String,
        language: String,
        vote: Number,
        description: String,
    },
    data(){
        return{
            flags: ['it', 'en']
        }
        
    },
    methods:{
        
        
    }
}
</script>

<style scoped lang="scss">
@import  '@/style/variables.scss';

.cards{
   ul{
       list-style: none;

       .cover-img{
           width: 342px;
           position: relative;

           .info{
               width: 100%;
               height: 100%;
               background: rgba(0, 0, 0, 0.815);
               position: absolute;
               padding: 25px;
               top: 0px;
               font-size: 14px;
               font-weight: 300;
               color: white;
               filter: opacity(0.0);
               &:hover{
                   filter: opacity(1);
               }

               span{
                   font-weight: 700;
               }

               .star{
                   color: $star-color;
               }
           }

       }
   }

    .flag{
        width: 20px;
    }
}
</style>