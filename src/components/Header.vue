<template>
  <header class="d-flex align-items-center justify-content-between">
      <section class="left">
          <img src="../assets/boolflix.png" alt="">
          <ul>
              <li>
                  <a href="#">Home</a>
              </li>
              <li>
                  <a href="#">Serie Tv</a>
              </li>
              <li>
                  <a href="#">Film</a>
              </li>
              <li>
                  <a href="#">Aggiunti di recente</a>
              </li>
              <li>
                  <a href="#">La mia lista</a>
              </li>
          </ul>
      </section>

      <section class="right">
          <input @keyup.enter="getFilmList" v-model.trim="getSearchString" type="text" placeholder="
          Cerca Film o SerieTV">
          <button @click.prevent="getFilmList"><i class="fas fa-search"></i></button>
          <img class="profile" src="../assets/photo-profile.jpg" alt="">
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
@import  '@/style/variables.scss';

    header{
        background: $primary-color;
        align-items: center;
        position: fixed;
        top: 0;
        width: 100%;
        z-index: 1;

        .left{
            display: flex;
            align-items: center;

            img{
            width: 200px;
            margin: 10px 20px;
            }

            ul{
                display: flex;
                list-style: none;

                a{
                    text-decoration: none;
                    margin: 0 10px;
                    color: $secondary-color;
                    font-size: 14px;
                    font-weight: 600;
                    &:hover{
                        color: $custom-color;
                    }
                }
            }
        }
        
        
        section{
            padding: 10px;

            input{
                height: 30px;
                margin: 10px;
                background: rgb(63, 62, 62);
                border: none;
                border-radius: 10px;
                color:$secondary-color;
                outline: none;
            }
            button{
                border:none;
                background: none;
                color: white;
                font-size: 20px;
                margin-right: 20px;

                &:active{
                    color: $custom-color;
                }
            }
            .profile{
                width: 50px;
                margin-right: 20px;
                cursor: pointer;

                &:active{
                    border:2px solid $secondary-color;
                }
            }
        }
    }
    
</style>