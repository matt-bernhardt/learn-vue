<template>
  <div class="home">
    <img alt="MIT Libraries logo" src="../assets/logo-302fedc6-298f-4221-9cef-79550494eccf.jpg">
    <h1>Search Rebuilt</h1>
    <SearchForm @clicked="doSearch" />
    <SearchTarget
      v-if="query"
      type="Books & media"
      about="Books, ebooks, audio books, music, and videos at MIT."
      :query=query />
    <SearchTarget
      v-if="query"
      type="Articles & journals"
      about="Articles from a variety of periodicals, including scholarly journals and magazines at MIT."
      :query=query />
    <SearchTarget
      v-if="query"
      type="Archives & manuscripts collections"
      about="Unique and rare materials from MIT Distinctive Collections."
      :query=query />
  </div>
</template>

<script>
// @ is an alias to /src
import SearchForm from '@/components/SearchForm.vue'
import SearchTarget from '@/components/SearchTarget.vue'

export default {
  name: 'Home',
  data() {
    return {
      query: ''
    }
  },
  components: {
    SearchForm,
    SearchTarget,
  },
  methods: {
    doSearch: function(query) {
      this.query = query;
    }
  }
}
</script>
