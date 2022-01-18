<template>
  <main>
    <div class="select">
      <span class="selezionaGenere">Seleziona il genere:</span>
      <Select 
      @doSearch="genreCards($event)"
      />
    </div>
    <div class="container">
      <div class="row row-cols-5 p-5" v-if="arrayGenre">
        <!-- nome del figlio -->
        <Card 
        v-for="(card, index) in arrayGenre" :key="index" :image="card.poster" :name="card.title" :title="card.title" :author="card.author" :year="card.year"/>
      </div>
      <div v-else class="loading">
				<h1>Loading...</h1>
			</div>
    </div>
  </main>
</template>

<script>
// import axios
import axios from 'axios';
// import child
import Card from './Card.vue';
import Select from './Select.vue';

export default {
  name: 'Main',
  // importare child nei componenti
  components: {
    Card,
    Select
  },
  data() {
    return {
      arrayOringinal: null,
      generePredefinito: "all",
      arrayGenre: null
    };
  },
  mounted() {
  setTimeout(() => {
			this.getCards()
		}, 1000);
  },
  methods: {
    getCards() {
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((result) => {
        this.arrayOringinal = result.data.response;
        this.arrayGenre = result.data.response; 
      })
      .catch((error) => {
        console.log(error);
      });
    },
    genreCards(text) {
      this.arrayGenre = this.arrayOringinal;

        if (text !=='all') {
          this.arrayGenre = this.arrayGenre.filter(album => album.genre.toLowerCase() === text);
        } else {
          return this.arrayGenre;
        }
        return this.arrayGenre;
    }
  }
};
</script>

<style lang="scss">
  .select {
    padding-top: 10px;
    width: 100%;
    text-align: center;
    .selezionaGenere{
      color: white;
      margin-right: 10px;
    }
  }
  .loading {
    color: white;
    display: flex;
    justify-content: center;
    height: calc(100vh - 70px);
    align-items: center;
	}
</style>