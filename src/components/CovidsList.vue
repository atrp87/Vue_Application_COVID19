<template>
  <div>
    <h1>COVID-19 data:</h1>
    <ul>
      <list-covid v-for="(country, index) in covids.Countries" :country="covid" :key="index"></list-covid>
    </ul>
  </div>
</template>

<script>
import ListCovid from './ListCovid.vue';

export default {
  name: 'covid-list',
  props: ['covids'],
  components: {
    "list-covid": ListCovid
  }
}
</script>

<style scoped>

</style>