<template>
  <div id="app">
    <div class="editor-container">
      <div class="article-title-container">
        <editor placeholder="Title" @input="titleInput"></editor>
      </div>
      <editor placeholder="Article content" @input="contentInput"></editor>
    </div>
    {{contentHtml}}
    {{titleHtml}}
  </div>
</template>

<script>
import editor from '../editor'

export default {
  name: 'app',
  components: {
    editor
  },
  data: function () {
    return {
      saveTimeout: 1000,
      titleHtml: '',
      contentHtml: ''
    }
  },
  methods: {
    titleInput (rawHtml) {
      clearTimeout(this.timeout)

      this.titleHtml = rawHtml
      this.timeout = setTimeout(() => {
        this.save()
      }, this.saveTimeout)
    },
    contentInput (rawHtml) {
      clearTimeout(this.timeout)

      this.contentHtml = rawHtml
      this.timeout = setTimeout(() => {
        this.save()
      }, this.saveTimeout)
    },
    save () {
      console.log('saving')
    }
  }
}
</script>
