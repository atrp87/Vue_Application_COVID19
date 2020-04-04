  
<template>
    <div>
      <covids-list :covids='covids'></covids-list>
      <covid-detail :covid='covidSelect'></covid-detail>
  </div>

</template>

<script>

import { eventBus } from "@/main.js";
import CovidsList from './components/CovidsList.vue';
import CovidDetail from './components/CovidDetail.vue'
import ListCovid from './components/ListCovid.vue';
import CovidSelect from './components/CovidSelect.vue';

export default {
  name: 'app',
  data(){
    return {
    covids: [],
    trackCountry: [],
    covidSelect: null
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
    "covid-detail": CovidDetail,

  }
}
</script>

<style>
</style>