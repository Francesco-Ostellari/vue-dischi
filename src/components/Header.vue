<template>
  <header>
    <div class="container_header">
      <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang="scss">
  .container_header {
    padding: 10px 30px;
    width: 100%;
    height: 70px;
    background-color:#2E3A46;
    img {
      height: 100%;
    }
  }
</style>