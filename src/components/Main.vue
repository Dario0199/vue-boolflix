<template>
    <main>
        <div v-for="(film, index) in films" :key="film-`${index}`">
           <Card
                :first_title="film.title"
                :second_title="film.original_title"
                :language="film.original_language"
                :vote="film.vote_average"
           />
        </div>
    </main>
</template>

<script>
import Card from '@/components/Card.vue';

export default {
    name: 'Main',
    components: {
        Card,
    },
    props:{
        films: Array,
    }
}
</script>

<style scoped lang="scss">

</style>