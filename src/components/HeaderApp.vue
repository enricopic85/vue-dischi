<template>
    <header>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Spotify_App_Logo.svg/2048px-Spotify_App_Logo.svg.png" alt="">
         <select name="year" id="year" v-model="selected" >
            <option disabled value="">Scegli l'anno di pubblicazione</option>
            <option value="all">All</option>
            <option v-for="(year,i) in years" :key="i" :value=year @change="('filter',selected)" >{{year}} </option>
        </select>
    </header>
</template>

<script>
export default {
    props:{
        discs:Array,
        years:Array
    },
    data(){
        return{
            selected:''
        }
    }
}
</script>

<style lang="scss" scoped>
    header{
        width: 100%;
        height: 80px;
        line-height: 80px;
        background-color: black;
        display: flex;
        align-items: center;
        padding-left: 15px;
        justify-content: space-around;
        img{
            height: 60px;
        }
       
    }
</style>