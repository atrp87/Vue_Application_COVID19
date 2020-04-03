<template lang="html">
<li>{{ country.country}}</li>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'list-covid',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>