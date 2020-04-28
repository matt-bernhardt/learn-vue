<template>
	<div class="search-form">
		<input placeholder="Start your search" v-model="query">
		<p>You are searching for: {{ query }}</p>
	</div>
</template>

<script>
export default {
	data() {
		return {
			query: ""
		};
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
