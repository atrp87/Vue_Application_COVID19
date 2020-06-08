<template>
  <div>
    <h2>Tracked Countires:</h2>
    <ul>
      <!-- <covid-selected
        v-for="(country, index) in covids.Countires"
        :country="country"
        :key="index"
      >{{country.Country}}</covid-selected>-->
      <covid-selected
        v-for="(country, index) in covids"
        :country="country"
        :key="index"
      >{{country.Country}}</covid-selected>
      <!-- <covid-list
        v-for="(country, index) in country.covids"
        :country="country"
        :key="index"
      >{{country.Country}}</covid-list>-->
    </ul>
  </div>
</template>

<script>
import CovidSelected from "./CovidSelected.vue";

export default {
  name: "covid-list",
  props: ["country"],
  components: {
    "covid-selected": CovidSelected
  }
};
</script>

<style scoped>
</style>
