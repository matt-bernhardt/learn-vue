<template>
	<div class="search-form">
		<input placeholder="Start your search" v-model="query">
		<button v-on:click="newSearch">Search</button>
		<p v-if="newSearchQuery">You are searching for: {{ newSearchQuery }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			query: ""
		};
	},
	methods: {
		newSearch () {
			this.$emit('clicked', this.newSearchQuery);
		}
	},
	computed: {
		newSearchQuery: function () {
			// This may provide space for escaping or computation to be done
			// on the provided query.
			return this.query;
		}
	}
}
</script>

<style scoped>
div.search-form {
	background: #eaeaea;
	margin: 1rem;
	padding: 1rem;
}
</style>
