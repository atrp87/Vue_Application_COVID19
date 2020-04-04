<template>
  <div>
    <h3 v-on:click="handleClick"> {{covid.Country}}</h3>
    <!-- <button  v-on:click="addToFavourites">Favourite</button> -->
  </div>
</template>

<script>

import { eventBus } from '../main.js';

export default {
  name: 'covid-select',
  props: ['covid'],
  methods: {
    handleClick() {
      eventBus.$emit( 'covid-select', this.covid )
    },
  }
}

</script>

<style scoped>

</style>