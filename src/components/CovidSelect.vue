<template>
  <div>
    <h3 v-on:click="handleClick"> {{ covid.Country }}</h3>
    <button  v-on:click="addToTrack">Track</button>
  </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
  name: 'covid-select',
  props: ['covid'],
  
  methods: {
    handleClick() {
      eventBus.$emit( 'covid-select', this.country )
    },
  }
}

</script>

<style scoped>

</style>