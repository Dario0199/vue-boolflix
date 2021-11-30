<template>
    <div class="card">
         <ul>
             <li>
                 <img class="cover" :src="`https://image.tmdb.org/t/p/w185${image}`" :alt="image">
             </li>
            <li>Titolo: {{ first_title }}</li>
            <li>Titolo originale: {{ second_title }}</li>
            <li>
                Lingua:
                <img class="flag" v-if="flags.includes(language)" :src="require(`../assets/${language}.png`)" :alt="language"> 
                <span v-else>{{ language }}</span>
            </li>
            <li>Voto: {{ vote }}</li>
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
.card{
   ul{
       list-style: none;
   }

    .flag{
        width: 20px;
    }
}
</style>