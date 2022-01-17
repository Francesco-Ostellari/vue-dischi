<template>
  <div class="col pb-3">
    <div class="card_spotify">
      <div class="container-img">
        <img :src="image" :alt="name">
      </div>
      <div class="title">
        {{title}}
      </div>
      <div class="author">
        {{author}}
      </div>
      <div class="date">
        {{year}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  // nome del figlio
	name: "Card",
	props: [
		'image',
		'name',
		'title',
		'author',
		'year'
	]
}
</script>

<style lang="scss">
  .card_spotify {
    width: 200px;
    height: 350px;
    padding: 20px;
    background-color:#2E3A46;
    .container-img{
      img {
        width: 100%;
      }
    }
    .title {
      color: white;
      margin-top: 15px;
      text-align: center;
      font-size: 1.4em;
      font-weight: bold;
    }
    .author {
      text-align: center;
      color: #788080;
      font-weight: bold;
    }
    .date {
      text-align: center;
      color: #788080;
      font-weight: bold;
    }
  }
</style>