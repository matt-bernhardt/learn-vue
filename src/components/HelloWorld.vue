<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Quick search at the MIT Libraries can be used to find books, movies, music, articles, journals, archives and manuscript colldctions, and other great stuff we have at the library.
    </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
