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
@import "./styles/app.scss"
</style>
