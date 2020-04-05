<template>

<div>
     <h1>Track Country</h1>
   <ul>
     <li v-for="(country, index) in trackCovids" :trackCovid="trackCovid" :key="index">{{trackCovid.name}} <button v-on:click="removeFromTrack" >remove</button> </li>
   </ul>
</div>

</template>

<script>

import { eventBus } from '../main.js'

export default {
    name: 'track-country',
    props: ['trackCountrys'],
    methods: {
      removeFromTrack: function(){
        eventBus.$emit( 'remove-covid', trackCountry)
      }
    }
}
</script>

<style>

</style>