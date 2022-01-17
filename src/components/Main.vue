<template>
  <main>
    <div class="container">
      <div class="row row-cols-5 p-5">
        <Card 
        v-for="(card, index) in cards" :key="index" :image="card.poster" :name="card.title" :title="card.title" :artist="card.author" :year="card.year"/>
      </div>
    </div>
  </main>
</template>

<script>
import axios from 'axios';
import Card from './Card.vue';

export default {
  name: 'Main',
  components: {
    Card,
  },
  data() {
    return {
      cards: null
    };
  },
  mounted() {
    this.getCards();
  },
  methods: {
    getCards() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((result) => {
        this.cards = result.data.response;
      })
      .catch((error) => {
        console.log(error);
      });
    },
  }
};
</script>

<style lang="scss">
  
</style>