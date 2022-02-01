<template>
    <header>
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/7/74/Spotify_App_Logo.svg/2048px-Spotify_App_Logo.svg.png" alt="">
         <select name="year" id="year" v-model="selected"  @change="$emit('filter',selected)">
            <option disabled value="">Scegli l'anno di pubblicazione</option>
            <option value="all">All</option>
            <option v-for="(year,i) in years" :key="i" :value=year >{{year}} </option>
        </select>
        <select name="genre" id="genre" v-model="gender"  @change="$emit('genere',gender)">
            <option disabled value="">Scegli il genere</option>
            <option value="all">All</option>
            <option v-for="(gender,i) in genre" :key="i" :value=gender >{{gender}} </option>
        </select>
    </header>
</template>

<script>
export default {
    props:{
        discs:Array,
        years:Array,
        genre:Array
    },
    data(){
        return{
            selected:'',
            gender:''
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