<template>
    <div class="container-card">
        <card-app v-for="(disc,i) in discs" 
        :key="i"
        :disco="disc"
        :genre="genre"
        :genreUser="genreUser"
        :valueUser="valueUser"/>
    </div>
</template>

<script>
import CardApp from './CardApp.vue'
export default {
  components: { CardApp },
    props:{
        discs: Array,
        valueUser:String,
        genre:Array,
        genreUser:String
    },
   
}
</script>

<style lang="scss" scoped>
    .container-card{
        display: flex;
        width: 1150px;
        flex-wrap: wrap;
        margin: 0 auto;
        padding-top: 50px;
        gap: 30px;
        justify-content: center;
    }
</style>