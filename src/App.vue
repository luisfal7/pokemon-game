<template>
  <pokemon-page />
  <pokemon-picture />
  <pokemon-options />
</template>

<script>
import PokemonOptions from './components/PokemonOptions.vue'
import PokemonPicture from './components/PokemonPicture.vue'
import PokemonPage from './pages/PokemonPage.vue'

export default {
  name: 'App',
  components: {
    PokemonPage,
    PokemonOptions,
    PokemonPicture
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
