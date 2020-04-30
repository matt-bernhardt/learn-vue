<template>
	<div class="search-target">
		<h2>{{ type}}</h2>
		<p>{{ about }}</p>
		<p><router-link to="/record">Record</router-link></p>
        <ul v-for="result in results" v-bind:key="result.id">
            <li>
                {{ result.title }}
                <span>{{ result }}</span>
                }
            </li>
        </ul>
	</div>
</template>

<script>
export default {
  props: {
    type: String,
    about: String,
    results: Array
  },
  created() {
    var placeholder = {
        'id':'TBD',
        'title':'Loading...'
    }
    this.results = Array()

    this.results.push(placeholder)
  },
  mounted() {
    this.axios
      .get('https://timdex.mit.edu/api/v1/search?q=whatever')
      .then(response => ( this.results = response.data.results ))
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