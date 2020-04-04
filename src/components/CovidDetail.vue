<template>
    <div v-if='covid'>
        <h2>{{ covid.Country}}</h2>
        <p>{{ covid.TotalConfirmed }}</p>
        <p>{{ covid.TotalDeaths}}</p>
        <p>{{ covid.TotalRecovered}}</p>
        <button v-if="!trackCovids.includes(covid)" v-on:click="addToTrack">Track Country</button>
    </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'covid-detail',
    props: ['covid', 'trackCovids'],

    methods: {
    addToTrack: function() {
        eventBus.$emit('track-covid', this.covid)
    }
    }
}
</script>

<style lang="stylus" scoped>
</style>
