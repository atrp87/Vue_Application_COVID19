<template>
<div>
    <h1>Cases:</h1>
   <ul>
   <li v-for="(favCovid, index) in favCovids" :favCovid="favCovid" :key="index">{{favCovid.Country}} <button v-on:click="removeFromFavourite" >Remove Country</button> </li>
   </ul>
   </div>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'favourited-covid',
    props: ['favCovids'],
    methods: {
      removeFromFavourite: function(){
        eventBus.$emit( 'remove-covid', favCovid)
      }
    }
}
</script>

<style>
</style>