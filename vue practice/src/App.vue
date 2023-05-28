<script setup>
import BaseCounter from './components/base-counter.vue';
import UserCard from './components/user-card.vue';
</script>

<template>
  <BaseCounter />
  <UserCard :user="{ name: 'Ben', food: 'Ramen' }" />
</template>


<style>
html{
  background-color: papayawhip;
}

button {
  border: 3px solid green;
}
</style>


<!-- script -->
<!-- // // https://pokeapi.co/api/v2/pokemon?limit=151

  export default {
  components: {
    Pokedex,
  },
}

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
// } -->

<!-- template -->
<!-- <pre>{{ pokedex }}</pre>
  <button @click="fetchPokemon">Fetch Pokemon</button> -->
  <!-- <h1>New App</h1>
  <Suspense>
    <Pokedex region="Hoenn" />

    <template v-slot:fallback> Loading Pokedex data... </template>
  </Suspense> -->
  