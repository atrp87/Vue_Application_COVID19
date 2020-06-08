<template>
  <div>
    <covid-list :covids="covids"></covid-list>
    <covid-detail :country="selectedCovid" :favCovid="favouriteCovid"></covid-detail>
    <favourited-covid :favCovids="favouriteCovid"></favourited-covid>
  </div>
</template>
 
<script>
import FavouritedCovid from "./components/FavouritedCovid";
import CovidList from "./components/CovidList.vue";
import CovidDetail from "./components/CovidDetail.vue";
import { eventBus } from "./main";

export default {
  data() {
    return {
      covids: [],
      favouriteCovid: [],
      selectedCovid: null
    };
  },
  components: {
    "covid-list": CovidList,
    "covid-detail": CovidDetail,
    "favourited-covid": FavouritedCovid
  },
  mounted() {
    fetch("https://api.covid19api.com/summary")
      .then(res => res.json())
      .then(covidsRes => (this.covids = covidsRes));

    eventBus.$on("covid-selected", covid => {
      this.selectedCovid = covid;
    });

    eventBus.$on("favourited-covid", covid => {
      this.favouriteCovid.push(covid);
    });

    eventBus.$on("remove-covid", favCovid => {
      const index = this.favouriteCovid.indexOf(favCovid);
      console.log(favCovid);

      console.log(index);

      this.favouriteCovid.remove(favCovid);
    });
  }
};
</script>

<style scoped>
h1 {
  color: red;
}
</style>