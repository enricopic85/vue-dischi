<template>
  <div id="app">
    <loader-app/>
   <header-app/>
   <main-app :discs="discs"/>
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
      discs:[]
    }
  },
   mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
        this.discs=response.data.response;
    })
  }
}
</script>

<style lang="scss">
 @import './style/main.scss';
</style>
