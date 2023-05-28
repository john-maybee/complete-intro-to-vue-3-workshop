<script>
import {newCount} from '../composables/countStore';

export default {
    setup() {
        return {
            newCount,
        }
    },

    data: () => ({
        count: 10,
        counterTitle: 'Counter Standard',
        incrementAmount: 3
    }),
    computed: {
        displayTitle() {
        if (this.count > 20) {
            return 'Counter Standard - Very Long'
        } else {
            return 'Counter Standard'
        }
        },
        optimizedIncrementAmount() {
        return this.displayTitle.length * this.incrementAmount
        }
    },
    methods: {
        // changeIncrementAmount(event){
        //   this.incrementAmount = event.target.value
        // },
        incrementCount(newAmount, event) {
        console.log(newAmount)
        console.log(event)
        this.count += this.optimizedIncrementAmount 
        this.newCount += 10;
        }
    },
}
</script>

<template>
    <h1>{{ displayTitle }}</h1>
    <h2>{{ newCount }}</h2>
      <p :data-increment-by="incrementAmount">{{ count }}</p>
      <button v-on:click="incrementCount">Increment Count</button>
      <!-- could just do @click="incrementCount" -->
      <h4>{{ incrementAmount }}</h4>
      <p>{{ optimizedIncrementAmount }}</p>
      <div>
        <label for="incrementAmount">Increment by:</label>
        <input 
          type="number" 
          v-model="incrementAmount"
        />
      </div>
</template>