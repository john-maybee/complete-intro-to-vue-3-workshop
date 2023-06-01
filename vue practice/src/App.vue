<script setup>
import BaseCounter from './components/base-counter.vue';
import UserCard from './components/user-card.vue';
import { ref } from 'vue';

const colorPreference = ref('white');

</script>

<template>
  <div class="wrapper">
    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/pokedex">Pokedex</router-link>
    </nav>
    <router-view />
    <h2> {{ colorPreference }}</h2>
    <input type="color" v-model="colorPreference" />
    <BaseCounter />
    <UserCard :user="{ name: 'Ben', food: 'Ramen' }" />
  </div>
</template>



<style>
html{
  background-color: papayawhip;
}

.wrapper {
  background-color: v-bind(colorPreference);
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
  