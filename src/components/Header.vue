<template>
  <header>
      <section>
          <input v-model.trim="getSearchString" type="text" placeholder="
          Search films">
          <button @click.prevent="getFilmList">Search</button>
      </section>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            getSearchString: '',
        }
        
    },
    methods:{
        getFilmList(){
            if(this.getSearchString !== ''){
                this.$emit('getValueInput', this.getSearchString);
                this.getSearchString = '';
            }
        }
    }
}
</script>

<style scoped lang="scss">

</style>