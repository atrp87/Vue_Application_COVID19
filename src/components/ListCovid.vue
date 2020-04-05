<template lang="html">
	<li v-on:click="handleClick">{{ country.Country }}</li>
</template>

<script>

import { eventBus } from '../main';
import CovidSelect from './CovidSelect.vue';

export default {
	name: 'list-covid',
	props: ['country'],
	components: {
		'covid-select': CovidSelect,
	},
	methods: {
		handleClick() {
			eventBus.$emit('covid-select', this.country);
		}
	}
}
</script>


<style lang="css" scoped>

</style>