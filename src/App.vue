<template>
  <div id="app">
    <!-- collegare file esterni -->
    <Header />
    <Main />
    <Footer />
  </div>
</template>

<script>
// importare i file esterni
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
// importare bootstrap
@import "~bootstrap/scss/bootstrap";
body  {
  background-color: #1E2D3B;
  width: 100%;
  height: 100vh;
}
</style>