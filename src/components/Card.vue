<template>
    <div class="card">
         <ul>
            <li>Titolo: {{ first_title }}</li>
            <li>Titolo originale: {{ second_title }}</li>
            <li>Lingua: {{ language}}</li>
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

    }
}
</script>

<style scoped lang="scss">

</style>