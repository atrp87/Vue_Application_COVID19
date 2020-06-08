  <template>
  <div v-if="country">
    <h2>{{ country.Country }}</h2>
    <p>Total Confirmed: {{ country.TotalConfirmed }}</p>
    <p>Total Deaths: {{ country.TotalDeaths }}</p>
    <p>Total Recovered: {{ country.TotalRecovered }}</p>
    <button v-if="!favCovids.includes(country)" v-on:click="addToFavourites">Track Country</button>
  </div>
</template>

<script>
import { eventBus } from "../main.js";
export default {
  name: "covid-detail",
  props: ["country", "favCovids"],
  methods: {
    addToFavourites: function() {
      eventBus.$emit("favourited-covid", this.covid);
    }
  }
};
</script>

<style scoped >
</style>