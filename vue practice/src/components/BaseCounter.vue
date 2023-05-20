<script>
export default {
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
        }
    },
}
</script>

<template>
    <h1>{{ displayTitle }}</h1>
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