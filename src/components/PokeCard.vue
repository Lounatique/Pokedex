<template>
    <div class="container">
        <div class="card flexcontainer">
            <span>{{ pokemon.pokedex_number}}</span>
            <img :src='imgpath'>
            <span>{{ pokemon.name }}</span>
            <img :src='imgtype1' class="type">
            <img v-if="pokemon.type2" :src='imgtype2' class="type">
        </div>
    </div>
</template>

<script>
    export default {
        props:{
            pokemon :{
                type : Object,
                required: true
            }
        },
        computed: {
            imgpath(){
                return "/images/"+this.pokemon.name.toLowerCase()+".png"
            },

            imgtype1(){
                return "/images/ImgType/"+this.pokemon.type1+".svg"
            },

            imgtype2(){
                
                return "/images/ImgType/"+this.pokemon.type2+".svg"

            }
        }

    }
</script>
<style scoped>

 .container{
    width: 80%;
    margin: auto;
 }

 .flexcontainer{
    display: flex;
    justify-content: space-between;
 }

 h3{
    font-size: 30px;
    color: white;
 }

 span{
    font-size: 25px;
    color: white;
 }
 
.card{
    margin: 1em;
    padding:1em;
    border-radius: 15px;
    border: 2px solid white;
}

.type{
    width: 50px;
}

</style>