<template>
  <h1>¿Quién este pokémon?</h1>
  <pokemon-picture :pokemonId="140" :showPokemon="true"/>
  <pokemon-options />
</template>

<script>
import PokemonOptions from './components/PokemonOptions.vue'
import PokemonPicture from './components/PokemonPicture.vue'

import getPokemonOptions from '@/helpers/getPokemonOptions'

export default {
  name: 'App',
  components: {
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
