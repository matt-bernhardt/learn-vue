<template>
	<div class="search-target">
		<h2>{{ type}}</h2>
		<p>{{ about }}</p>
		<p><router-link to="/record">Record</router-link></p>
	</div>
</template>

<script>
export default {
  props: {
    type: String,
    about: String
  }
}
</script>

<style scoped>
div.search-target {
	background: #eaeaea;
	border-top: 0.25rem solid black;
	border-bottom: 1px solid black;
	margin: 1rem;
	margin-bottom: 2rem;
}
</style>