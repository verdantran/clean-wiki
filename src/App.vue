<template>
  <div id="app">
    <NewArticle />
  </div>
</template>

<script>
import NewArticle from './components/newArticle/NewArticle.vue'

export default {
  name: 'app',
  components: {
    NewArticle
  }
}
</script>

<style lang="scss">
 #app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
