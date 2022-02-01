<template>
  <div id="app">
    <loader-app v-if="loading"/>
    <header-app :years="years"/>
    <main-app :discs="discs"  />
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
      loading:true,
      years:[]
    }
  },
   mounted(){
     setTimeout(() => {
       axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
        this.discs=response.data.response;
        for(let i=0;i<this.discs.length;i++){
              if (!this.years.includes(this.discs[i].year)) {
                this.years.push(this.discs[i].year)
              }
        }
        this.loading=false;
    })
     }, 3000);
    
  }
}
</script>

<style lang="scss">
 @import './style/main.scss';
</style>
