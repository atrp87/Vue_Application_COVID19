  
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
// import TrackCountry from './components/CovidCountry.vue';

export default {
  name: 'app',
  data(){
    return {
    covids: [],
    trackedCountry: [],
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
    eventBus.$on ('tracked-country', (covid)=> {
      this.trackCountry.push(covid);
    })
    eventBus.$on ('remove-track', (tCovids)=> {
      const index = this.trackCountry.indexOf(tCovids)
      console.log(index);
      
      console.log(index);
      
      this.trackCountry.remove(tCovids)
    })
  },

  components: {
    "covids-list": CovidsList,
    "covid-detail": CovidDetail,
    "list-covid": ListCovid

  }
}
</script>

<style>
</style>