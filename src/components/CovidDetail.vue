  <template>
  <div v-if='covid'>
    <h2>{{ covid.Country }}</h2>
      <p>Total Confirmed: {{ covid.TotalConfirmed }}</p>
      <p>Total Deaths: {{ covid.TotalDeaths }}</p>
      <p>Total Recovered: {{ covid.TotalRecovered }}</p>
    <button v-if="!favCovids.includes(covid)" v-on:click="addToFavourites">Track Country</button>
  </div>
</template>

<script>
import { eventBus } from '../main.js';
export default {
    name: 'covid-detail',
    props: ['covid', 'favCovids'],
    methods: {
        addToFavourites: function(){
          eventBus.$emit( 'favourited-covid', this.covid)
    }
  }
}
</script>

<style scoped >

</style>