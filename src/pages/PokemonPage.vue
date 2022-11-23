<template>
  <h1>¿Quién es este pokémon?</h1>
  <pokemon-picture :pokemonId="140" :showPokemon="true" />
  <pokemon-options :pokemons="pokemonArr" />
</template>

<script>
import PokemonOptions from "@/components/PokemonOptions.vue";
import PokemonPicture from "@/components/PokemonPicture.vue";

import getPokemonOptions from "@/helpers/getPokemonOptions";

export default {
  components: {
    PokemonOptions,
    PokemonPicture,
  },
  data() {
    return {
      pokemonArr: [],
    };
  },
  methods: {
    async mixPokemonArray() {
      this.pokemonArr = await getPokemonOptions();
      console.log(this.pokemonArr);
    },
  },
  mounted(){
    this.mixPokemonArray()
  }
};
</script>

<style></style>
