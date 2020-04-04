<template>
    <div v-if='covid'>
        <h2>{{ covid.Country}}</h2>
        <p>{{ covid.TotalConfirmed }}</p>
        <p>{{ covid.TotalDeaths}}</p>
        <p>{{ covid.TotalRecovered}}</p>
    </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
    name: 'covid-detail',
    props: ['covid']

}
</script>

<style lang="stylus" scoped>

</style>