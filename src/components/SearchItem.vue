<template>
	<li class="search-item">
		<h3><a :href="result.source_link">{{ result.title }}</a></h3>
		<p>{{ result.content_type }}</p>
	</li>
</template>

<script>
export default {
	props: {
		result: Object,
	}
}
</script>

<style scoped>
li.search-item {
	border: 1px solid #696969;
	list-style-type: none;
	padding: 0.5rem;
	margin-bottom: 1rem;
	text-align: left;
}
</style>
