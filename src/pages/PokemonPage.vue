<template>
  <h1 v-if="!pokemon">Espere por favor...</h1>
  <div v-else>
    <h1>¿Quién es este pokémon?</h1>
    <pokemon-picture :pokemon-id="pokemon.id" :show-pokemon="showPokemon" />
    <pokemon-options :pokemons="pokemonArr" @selection="checkAnswer($event)" />
  </div>
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
      pokemon: null,
      showPokemon: false,
    };
  },
  methods: {
    async mixPokemonArray() {
      this.pokemonArr = await getPokemonOptions();
      console.log(this.pokemonArr);

      const rndInt = Math.floor(Math.random() * 4);
      this.pokemon = this.pokemonArr[rndInt];
    },
    checkAnswer(pokemonId) {
      console.log("Pokemon page", pokemonId);
      this.showPokemon = true;
    },
  },
  mounted() {
    this.mixPokemonArray();
  },
};
</script>

<style></style>
