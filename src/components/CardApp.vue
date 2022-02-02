<template>
    <div>
        <div class="card-app" >
            <div class="img">
                <img :src="disco.poster" alt="">
            </div>
            <h4>{{disco.title}}</h4>
            <p>{{disco.autor}}</p>
            <p>{{disco.year}}</p>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        disco:Object,
        years:Array,
        valueUser:String,
        genre:Array,
        genreUser:String
    }
}
</script>

<style lang="scss" scoped>
   div{
       display: flex;
       justify-content: center;
       align-items: center;
        .card-app{
        width: 180px;
        height: 320px;
        display: flex;
        align-items: center;
        padding-top: 10px;
        background-color: rgb(68, 59, 107);
        flex-direction: column;
        .img{
            width: 120px;
            height: 120px;
            img{
                width: 100%;
            }
        }
        h4{
            text-transform: uppercase;
            color: white;
            padding-bottom: 20px;
            padding-top: 20px;
            text-align: center;
        }
        p{
            color: white;
        }
    }
   }
</style>