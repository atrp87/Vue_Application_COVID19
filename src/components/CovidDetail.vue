<template>
    <div v-if='covid'>
        <h2>{{ covid.Country}}</h2>
        <p>Total Confirmed: {{ covid.TotalConfirmed }}</p>
        <p>Total Deaths: {{ covid.TotalDeaths }}</p>
        <p>Total Recovered: {{ covid.TotalRecovered }}</p>
        <button>hi</button>
        <!-- <button v-if="!tCovids(covid)" v-on:click="addToTrack">Track Country</button> -->
    </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'covid-detail',
    props: ['covid', 'tCovids'],

    methods: {
    addToTrack: function() {
        eventBus.$emit('track-covid', this.covid)
    }
  }
}
</script>

<style lang="stylus" scoped>
</style>
