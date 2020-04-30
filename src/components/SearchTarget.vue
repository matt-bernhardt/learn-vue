<template>
    <div class="search-target">
        <h2>{{ type}}</h2>
        <p>{{ about }}</p>
        <ul>
            <li
                is="SearchItem"
                v-for="(result, index) in results"
                v-bind:result="result"
                v-bind:index="index"
                v-bind:key="result.id"></li>
        </ul>
    </div>
</template>

<script>
import SearchItem from '@/components/SearchItem.vue'

export default {
  components: {
    SearchItem,
  },
  props: {
    type: String,
    about: String,
    results: Array,
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