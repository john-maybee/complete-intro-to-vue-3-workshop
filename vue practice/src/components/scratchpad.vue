<script>
import BaseCounter from './components/BaseCounter.vue';
import UserCard from './components/user-card.vue';
import BaseButton from './components/base-button.vue';
import BaseLayout from './components/base-layout.vue';

export default {
  components: {
    BaseCounter,
    UserCard,
    BaseButton,
    BaseLayout,
  },
  data() {
          return {
            count: 10,
            counterTitle: 'Counter Standard',
            incrementAmount: 3,
            message: 'Hello it works',
            listOfNumbers: [
              {
                name: 1,
                id: '6a887cd2-f0bf-4321-b192-92016f82a883',
                list: [1, 2, 3]
              },
              {
                name: 2,
                id: '8d14d90b-2d47-473e-8293-d5c324111d0d',
                list: [1, 2, 3]
              },
              {
                name: 3,
                id: 'cd806d65-2309-4625-9104-dcd636cd79b5',
                list: [1, 2, 3]
              },
              {
                name: 4,
                id: '00c939cd-fbf4-46d0-8e61-0bc2ce8a5332',
                list: [1, 2, 3]
              },
              {
                name: 5,
                id: '295a8170-59c1-4462-9de1-3c9cd41cedab',
                list: [1, 2, 3]
              }
            ],
            userData: {
              name: 'Ben',
              preferredFramework: 'Vue',
              favoriteFood: 'Pizza',
              favoriteNumbers: [3, 7, 12]
            }
          }
        },
        methods: {
          changeName() {
            this.userData.name = "Charlie";
          },
        }
        
        
        // watch: {
        //   count(newValue) {
        //     // console.log(newValue)
        //     if (newValue > 20) {
        //       this.counterTitle += ' Very Long'
        //     }
        //   }
        // }
};
</script>

<template>
  <BaseLayout>
    <template v-slot:sidebar>
      Aside
    </template>
    <template v-slot:main>
      <UserCard :user="userData" @change-name="changeName" />
    </template>
    <template v-slot:footer>
      <BaseCounter />
    </template>
  </BaseLayout>
  <BaseButton :left="true">
    <!-- {{ userData.name }} -->
    <!-- Arrow Left - Hi! (Can enter writing in here to override the text that is within the slot in the base-button component) -->
  </BaseButton>
  <UserCard :user="userData" @change-name="changeName" />
  <hr />

  <p v-if="message.length % 2 === 0">Even: {{ message.toUpperCase() }}</p>
  <p v-else>Odd: {{ message }}</p>
  <ul v-for="(item, index) in listOfNumbers" :key="`item-${index}`">
    <li>
      {{ item.id }}
      <ul>
        <li v-for="number in item.list" :key="`number-${index}`">{{ number }}</li>
      </ul>
    </li>
  </ul>
  <hr />
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>