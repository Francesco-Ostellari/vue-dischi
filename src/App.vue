<template>
  <div id="app">
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';
export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data() {
    return {
      
    };
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
body  {
  background-color: #1E2D3B;
  width: 100%;
  height: 100vh;
}
</style>