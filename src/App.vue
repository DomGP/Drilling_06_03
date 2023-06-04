<template>
  <div id="app">
        <Games
        :games="games"
        @eliminarGame="eliminar"/>
  </div>
</template>

<script>
import Games from "./components/Games.vue";

export default {
  name: "App",
  data(){
    return{
      games: ["Arena of valor", "Pokemon Unite", "Donkey Kong", "Heroes of the storm", "Valorant"]

    }
  },
  components: {
    Games,
  },
  methods:{
    eliminar(index){
      this.games.splice(index,1)
    }

  },
  
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
