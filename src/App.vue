<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo-302fedc6-298f-4221-9cef-79550494eccf.jpg">
    <h1>Search Rebuilt</h1>
    <p>
      Quick search at the MIT Libraries can be used to find books, movies, music, articles, journals, archives and manuscript colldctions, and other great stuff we have at the library.<br />
      This is a re-imagined version of <a href="https://lib.mit.edu">the primary search gateway for the MIT Libraries.</a>
    </p>
    <SearchForm />
    <SearchTarget
      type="Books & media"
      about="Books, ebooks, audio books, music, and videos at MIT."/>
    <SearchTarget
      type="Articles & journals"
      about="Articles from a variety of periodicals, including scholarly journals and magazines at MIT."/>
    <SearchTarget
      type="Archives & manuscripts collections"
      about="Unique and rare materials from MIT Distinctive Collections."/>
  </div>
</template>

<script>
import SearchForm from './components/SearchForm.vue'
import SearchTarget from './components/SearchTarget.vue'

export default {
  name: 'App',
  components: {
    SearchForm,
    SearchTarget
  }
}
</script>

<style>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
