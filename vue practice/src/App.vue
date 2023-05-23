<script>
import Pokedex from './components/pokedex.vue';

export default {
  components: {
    Pokedex,
  },
}
// // https://pokeapi.co/api/v2/pokemon?limit=151

// export default {
//   async setup() {
//     const regionName = 'Kanto';
    
//     const pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
//       .then(response => response.json());
//     return {
//       pokedex,
//       regionName,
//     };
//   },
//   data: () => ({
//     pokedex: [1, 2, 3],
//   }),
//   // methods: {
//   //   async fetchPokemon() {
//   //     this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
//   //     .then(response => response.json());
//   //   }
//   // },
//   // beforeCreate() {
//   //   console.log('beforeCreate')
//   //   console.log(this.pokedex)
//   // },
//   created() {
//     // this.fetchPokemon();

//     console.log(this.regionName);
//     console.log(this.pokedex);
//   },
// }
</script>

<template>
  <h1>New App</h1>
  <Suspense>
    <Pokedex />

    <template v-slot:fallback> Loading Pokedex data... </template>
  </Suspense>
  <!-- <pre>{{ pokedex }}</pre>
  <button @click="fetchPokemon">Fetch Pokemon</button> -->
</template>

<style></style>