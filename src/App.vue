<template>
  <div id="header" class="flexContainer container">
    <h2>Create your own pokedeck</h2>
    <img id="LogoPrincipal" alt="Vue logo" src="./assets/LogoPokemon.png">
    <h2>and fight with other in arena !</h2>
  </div>
  <HelloWorld id="msgHeader" class="container" msg="Welcome to My Pokedeck! From the drop-down list below, select the 5 pokémons of your choice to make up your pokedeck, which you'll find by clicking on the button at the bottom of this page. Once you've created your pokedeck and have 100% confidence in the pokémons you've chosen, enter the arena to defend your values! Catch them all!"/>
<main>
  <PokeList />
</main>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import PokeList from './components/PokeList.vue'


export default {
  name: 'App',
  components: {
    HelloWorld,
    PokeList

  }
}
</script>

<style>
#app {
  font-family: 'Caveat Brush', cursive;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
}
#LogoPrincipal {
  width: 30%;
}

.flexContainer{
  display: flex;
  justify-content: space-between;
}
 .container{
  width: 80%;
  margin: auto;
 }

 #header{
  align-items: center;
 }

 body{
  background-image: url(./assets/background.png); 
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  /*background-color: wheat;*/
 }

 #msgHeader{
  font-size: 13px;
  margin-top: 10vh;
 }
 h2{
  font-size: 25px;
 }
</style>
