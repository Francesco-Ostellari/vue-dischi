<template>
  <select v-model="generePredefinito" @change="$emit('doSearch', generePredefinito)" name="genere" id="genere">
    <option value="all">All</option>
    <option value="rock">Rock</option>
    <option value="pop">Pop</option>
    <option value="jazz">Jazz</option>
    <option value="metal">Metal</option>
  </select>
</template>

<script>
export default {
  name: 'Select',
  data () {
    return {
      generePredefinito: 'all'
    }
  }
}
</script>

<style>

</style>