<template>
        <div id="barreInfo" class="container flexcontainer">
            <h3>Numéro</h3>
            <h3>Image</h3>
            <h3>Nom</h3>
            <h3>Type 1</h3>
            <h3>Type 2</h3>
        </div>

    
    <Teleport to="body">
        <div v-if="selectedPokemon!=null" class="modal">
            <div class="container flexcontainer">
                <img :src='imgpath'>
                <span>{{ selectedPokemon.name }}</span>
            </div>
            <div id="stats" class="container flexcontainer">
                <div class="">
                    <p>Pokemon base health</p>
                    <span>{{ selectedPokemon.hp }}</span>
                </div>
                <div>
                    <p>Pokemon base attack</p>
                    <span>{{ selectedPokemon.attack }}</span>
                </div>
                <div>
                    <p>Pokemon base defense</p>
                    <span>{{ selectedPokemon.defense }}</span>
                </div>
            </div>
            <div class="container">
                <button>Add to my pokeDeck</button>
            </div>
        </div>
    </Teleport>

    <div v-if="selectedPokemon!=null" class="layergrid" @click="selectedPokemon=null"></div>

    <PokeCard v-for="pokemon of pokemons" :key="pokemon" v-bind:pokemon="pokemon" @click="selectedPokemon = pokemon">
    </PokeCard>
</template>
<script>
import PokeCard from './PokeCard.vue'
import json_pokemon from'@/assets/pokemon.json'
export default {
  name: 'PokeList',
  components: {
    PokeCard
  },
  data(){
    return{
        pokemons : json_pokemon,
        selectedPokemon: null,
    }
  },
  computed: {
            imgpath(){
                return "/images/"+this.selectedPokemon.name.toLowerCase()+".png"
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
    align-items: center;
 }

 .flexcentered{
    justify-content: center;

 }
 #barreInfo{
    width:80%;
    margin: auto;
    padding-left: 30px;
    padding-right: 30px;

 }

 .modal{
    font-family: 'Caveat Brush', cursive;
    position: fixed;
    z-index: 2;
    top: 30%;
    left: 25%;
    background-color: black;
    color: white ;
    width: 50%;
    border-radius: 25px;
    border: 5px white solid;
    padding-bottom: 25px;
    font-size: 25px;
}

 .modal img{
    width: 30%;
 }

 .modal button{
    background-color: black;
    border: 3px solid white;
    border-radius: 20px;
    color: white;
    padding: 12px;
    margin-left: 250px;
 }

 .layergrid{
    background-color: black;
    opacity: 80%;
    position: fixed;
    z-index: 1;
    width: 100%;
    height: 100%;
    top: 0%;
    left: 0%;
 }
</style>