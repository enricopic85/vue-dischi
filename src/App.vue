<template>
  <div id="app">
    <loader-app v-if="loading"/>
    <header-app v-if="loading===false"/>
    <main-app :discs="discs" v-if="loading===false"/>
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue'
import MainApp from './components/MainApp.vue'
import axios from 'axios'
import LoaderApp from './components/LoaderApp.vue'
export default {
  name: 'App',
  components: {
    HeaderApp,
    MainApp,
    LoaderApp
  },
  data(){
    return{
      discs:[],
      loading:true
    }
  },
   mounted(){
     setTimeout(() => {
       axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
        this.discs=response.data.response;
        this.loading=false;
    })
     }, 5000);
    
  }
}
</script>

<style lang="scss">
 @import './style/main.scss';
</style>
