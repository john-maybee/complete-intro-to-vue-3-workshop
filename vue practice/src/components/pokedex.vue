<script>
// https://pokeapi.co/api/v2/pokemon?limit=151
import { computed, ref, reactive } from 'vue';

export default {
  async setup() {
    const regionName = ref('Kanto');

    const state = reactive({
      elementType: 'lightning',
    });

    console.log(state);

    const elementTypeAllCaps = computed(() => {
      return state.elementType.toUpperCase();
    });
    
    const pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
      .then(response => response.json());
    return {
        pokedex,
        regionName,
        elementTypeAllCaps,
    };
  },
  data: () => ({
    pokedex: [1, 2, 3],
  }),
  // methods: {
  //   async fetchPokemon() {
  //     this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
  //     .then(response => response.json());
  //   }
  // },
  // beforeCreate() {
  //   console.log('beforeCreate')
  //   console.log(this.pokedex)
  // },
  computed: {
    regionNameLowerCase() {
      return this.regionName.toLowerCase();
    }
  },
  methods: {
    changeRegionName() {
      this.regionName = 'Hoenn';
    }
  },
  created() {
    // this.fetchPokemon();

    console.log(this.regionName);
    console.log(this.pokedex);
  },
}
</script>

<template>
    <h2>{{ regionName }}</h2>
    <h3>{{ elementTypeAllCaps }}</h3>
    <h3>{{ regionNameLowerCase }}</h3>
    <button @click="changeRegionName">Change Region Name</button>
    <pre>{{ pokedex }}</pre>

    
</template>