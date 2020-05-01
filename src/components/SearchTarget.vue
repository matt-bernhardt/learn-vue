<template>
    <div class="search-target">
        <h2>{{ type}}</h2>
        <p>{{ about }}</p>
        <ul>
            <li
                is="SearchItem"
                v-for="(result, index) in results"
                :type="type"
                v-bind:result="result"
                v-bind:index="index"
                v-bind:key="result.id"></li>
        </ul>
    </div>
</template>

<script>
import SearchItem from '@/components/SearchItem.vue'

export default {
  name: 'SearchTarget',
  components: {
    SearchItem,
  },
  props: {
    about: String,
    query: String,
    results: Array,
    target: String,
    type: String,
  },
  methods: {
    conductSearch: function (term) {
      if (term) {
        if ('aspace' === this.target) {
          this.searchTimdexGraph(term);
        } else {
          this.searchTimdexJson(term);
        }
      }
    },
    searchTimdexJson: function (term) {
      this.axios
        .get('https://timdex.mit.edu/api/v1/search?q=' + term)
        .then(response => ( this.results = response.data.results ));
    },
    searchTimdexGraph: function (term) {
      this.axios({
        url: 'https://timdex.mit.edu/graphql',
        method: 'post',
        data: {
          query: `
            query ArbitraryName {
              search(searchterm: "` + term + `", source: "MIT ArchivesSpace") {
                hits
                records {
                  sourceLink
                  title
                  identifier
                  publicationDate
                  physicalDescription
                  summary
                  contributors {
                    value
                  }
                }
              }
            }
            `
        }
      }).then((result) => {
        this.results = result.data.data.search.records
      });
    }
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
    this.conductSearch(this.query);
  },
  watch: {
    'query': function() {
      this.conductSearch(this.query);
    }
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