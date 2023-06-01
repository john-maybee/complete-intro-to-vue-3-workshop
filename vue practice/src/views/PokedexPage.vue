<script setup>

</script>

<template>
    <h1>Pokedex</h1>
</template>

<style></style>

<!-- <script setup>
import BaseButton from '../components/base-button.vue';
import { computed, defineProps, defineEmits, ref, reactive } from 'vue';

const emits = defineEmits(['change-region']);

const props = defineProps({
    region: {
        type: String,
    },
});

const regionName = ref('Kanto');

const state = reactive({
    elementType: 'lightning',
});

console.log(state);

const elementTypeAllCaps = computed(() => {
    return state.elementType.toUpperCase() + props.region;
});

const pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
    .then(response => response.json());

const changeRegionName = () => {
    regionName.value = 'Hoenn';
    emits('change-region');
};
</script>

<template>
    <h2>{{ regionName }}</h2>
    <BaseButton />
    <h3>{{ elementTypeAllCaps }}</h3>
    <button @click="changeRegionName">Change Region Name</button>
    <pre>{{ pokedex }}</pre>
</template> -->

 <!-- <h3>{{ regionNameLowerCase }}</h3> -->
 <!-- // export default {
    //   async setup() { -->
<!-- // methods: {
    //   async fetchPokemon() {
    //     this.pokedex = await fetch('https://pokeapi.co/api/v2/pokemon?limit=151')
    //     .then(response => response.json());
    //   }
    // },
    // beforeCreate() {
    //   console.log('beforeCreate')
    //   console.log(this.pokedex)
    // },
  //   computed: {
  //     regionNameLowerCase() {
  //       return this.regionName.toLowerCase();
  //     }
  //   },
  //   methods: {
  //     changeRegionName() {
  //       this.regionName = 'Hoenn';
  //     }
  //   },
  //   created() {
  //     // this.fetchPokemon();
  
  //     console.log(this.regionName);
  //     console.log(this.pokedex);
  //   }, -->

  <!-- // return {
    //     changeRegionName,
    //     pokedex,
    //     regionName,
    //     elementTypeAllCaps,
    // };
//   }, -->
<!-- // } -->

<!-- data: () => ({
    pokedex: [1, 2, 3],
    }), -->

  <!-- // https://pokeapi.co/api/v2/pokemon?limit=151 -->