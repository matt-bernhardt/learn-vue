<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo-302fedc6-298f-4221-9cef-79550494eccf.jpg">
    <HelloWorld msg="About this search app"/>
    <SearchTarget type="Books"/>
    <SearchTarget type="Articles"/>
    <SearchTarget type="Archives and manuscripts" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import SearchTarget from './components/SearchTarget.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    SearchTarget
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
