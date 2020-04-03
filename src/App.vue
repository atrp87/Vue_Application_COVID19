<template>
    <div>
       <h1>COVID-19</h1>
      <covids-list :covids='covids'></covids-list>
  </div>

</template>

<script>

import { eventBus } from "@/main.js";

import CovidsList from './components/CovidsList.vue';

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
  },

  components: {
    "covids-list": CovidsList,
  }
}

</script>

<style>

</style>
