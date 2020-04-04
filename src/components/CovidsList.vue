<template>
  <div>
     <h1>Coronavirus Cases:</h1>
    <ul>
      <list-covid v-for="(country, index) in covids.Countries" :country="country" :key="index"></list-covid>
    </ul>
  </div>
</template>

<script>

import ListCovid from './ListCovid.vue';
import CovidSelect from './CovidSelect.vue';

export default {
  name: 'covid-list',
  props: ['covids'],
  components: {
    "list-covid": ListCovid,
  }
}
</script>

<style scoped>

</style>
