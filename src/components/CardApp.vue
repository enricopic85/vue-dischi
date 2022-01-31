<template>
    <div class="card-app">
        <div class="img">
            <img :src="disco.poster" alt="">
        </div>
        <h4>{{disco.title}}</h4>
        <p>{{disco.autor}}</p>
        <p>{{disco.year}}</p>
    </div>
</template>

<script>
export default {
    props:{
    disco:{
       title:String,
       poster:String,
       autor:String,
       year:String
    }
      
    }
}
</script>

<style lang="scss" scoped>
    .card-app{
        width: 180px;
        height: 320px;
        border: 1px solid black;
        display: flex;
        align-items: center;
        padding-top: 10px;
        background-color: grey;
        flex-direction: column;
        .img{
            width: 120px;
            height: 120px;
            border: 1px solid black;
            img{
                width: 100%;
            }
        }
        h4{
            text-transform: uppercase;
            color: white;
            padding-bottom: 20px;
            padding-top: 20px;
        }
        p{
            color: white;
        }
    }
</style>