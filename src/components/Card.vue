<template>
    <div class="card">
         <ul>
            <li>Titolo: {{ first_title }}</li>
            <li>Titolo originale: {{ second_title }}</li>
            <li>
                Lingua:
                <img v-if="flags.includes(language)" :src="require(`../assets/${language}.png`)" :alt="language"> 
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
    img{
        width: 20px;
    }
}
</style>