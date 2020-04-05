<template>

  <div>
    <button  v-on:click="addToTrack">Track</button>
  </div>
  
</template>

<script>

export default {
  name: 'covid-select',
  props: ['covid'], 
}

</script>

<style scoped>

</style>