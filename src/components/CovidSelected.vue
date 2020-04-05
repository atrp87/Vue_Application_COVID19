<template>
  <div>
<h3 v-on:click="handleClick"> {{county.Country}}</h3>

  </div>
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'covid-selected',
  props: ['covid'],
  methods: {
    handleClick(){
      eventBus.$emit( 'covid-selected', this.covid )
    },
    
  }
}
</script>

<style scoped>
</style>