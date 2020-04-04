<template>
    <div>
      <covids-list :covids='covids'></covids-list>
  </div>

</template>

<script>

import { eventBus } from "@/main.js";

import CovidsList from './components/CovidsList.vue';
import CovidDetail from './components/CovidDetail.vue'

export default {
  name: 'app',
  data(){
    return {
    covids: [],
    selectedCovid: null
     };
  },
  mounted(){
    fetch('https://api.covid19api.com/summary')
    .then(res => res.json())
    .then(covids => this.covids = covids)

    eventBus.$on ('covid-select', (covid) => {
      this.covidSelect = covid;
    })

  },
  components: {
    "covids-list": CovidsList,
    'covid-detail': CovidDetail,
  }
}

</script>

<style>

</style>
