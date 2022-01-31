<template>
  <div id="app">
   <header-app/>
   <main-app :discs="discs"/>
  </div>
</template>

<script>
import HeaderApp from './components/HeaderApp.vue'
import MainApp from './components/MainApp.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    HeaderApp,
    MainApp
  },
  data(){
    return{
      discs:[]
    }
  },
   mounted(){
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response)=>{
        this.discs=response.data
    })
  }
}
</script>

<style lang="scss">
 @import './style/main.scss';
</style>
