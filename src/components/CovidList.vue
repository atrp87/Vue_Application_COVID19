<template>
<div>
 <h2>Tracked Countires:</h2>
 <ul>
   <!-- <covid-selected v-for="(covid, index) in covids.Countires" :country="country" :key="index">{{covid.Country}}</covid-selected> -->
   <covid-list v-for="(country, index) in covids.Countries" :country="country" :key="index">{{country.Country}}</covid-list>
   </ul>
</div>
</template>

<script>

import CovidSelected from './CovidSelected.vue';

export default {
  name: 'covid-list',
  props: ['country'],
  components: {
    // 'covid-selected': SelectedCovid
  }
}
</script>

<style scoped>
</style>
