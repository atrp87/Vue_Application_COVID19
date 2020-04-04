<template>
<div>
    <h1>Track Country</h1>
   <ul>
   <li v-for="(trackcovid, index) in trackCovids" :trackCovid="trackCovid" :key="index">{{trackCovid.name}} <button v-on:click="removeFromTrack" >remove</button> </li>
   </ul>
   </div>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'track-covid',
    props: ['trackCovids'],

    methods: {
      removeFromTrack: function(){
        eventBus.$emit( 'remove-covid', trackCovid)
      }
    }
}
</script>

<style>
</style>