<template lang="html">
<li>{{ country.Country }}</li>

</template>

<script>

import CovidSelect from './CovidSelect.vue';

export default {
  name: 'list-covid',
  props: ['country'],
  components: {
    'covid-select': CovidSelect
  }
}
 
</script>

<style lang="css" scoped>
</style>