<template>
    <main>
        <div v-for="(film, index) in films" :key="film-`${index}`">
           <Card
                :image="film.poster_path"
                :first_title="film.title"
                :second_title="film.original_title"
                :language="film.original_language"
                :vote="film.vote_average"
                :description="film.overview"
           />
        </div>
        <div v-for="(series, index) in seriesData" :key="series-`${index}`">
            <Card
                :image="series.poster_path"
                :first_title="series.name"
                :second_title="series.original_name"
                :language="series.original_language"
                :vote="series.vote_average"
                :description="series.overview"
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
        seriesData: Array,
    }
}
</script>

<style scoped lang="scss">
main{
    padding-top: 100px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

</style>