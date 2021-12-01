<template>
  <div id="app">

    <Header @getValueInput="getSearch"/>

    <Main :films="filmsList" :seriesData="seriesList"/>

  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    Main,
  },
  data(){
        return {
          filmsList: null,
          seriesList: null,
          searchString: '',
            
        }
    },
    // created(){
    //     this.getValue()
    // },
    methods: {
        getValue(){
            axios.get('https://api.themoviedb.org/3/search/tv', {
              params: {
                api_key: 'a9afe8d25b0f316b8722fba1a304f377',
                query: this.searchString,
                language: 'it-IT'
              }
            })
            .then(results => {
              this.seriesList = results.data.results
            })
            .catch(error => {
              console.log(error);
            });

            axios.get('https://api.themoviedb.org/3/search/movie', {
                params: {
                    api_key: 'a9afe8d25b0f316b8722fba1a304f377',
                    query: this.searchString,
                    language: 'it-IT'
                },
            })
            .then(results => {
                console.log(results.data.results);
                this.filmsList = results.data.results
            })
            .catch(error => {
                console.log(error);
            })
        },
        
        getSearch(text){
         this.searchString = text;
         this.getValue()
        }
    }
}
</script>

<style lang="scss">
@import  '@/style/variables.scss';

#app{
  height: 100%;
  background: $primary-color;
}

</style>
