<template>
  <div id="app">
    <div class="editor-container">
      <div class="article-title-container">
        <medium-editor
          data-placeholder="Title"
          :text="articleTitle"
          v-on:edit="articleTitleEdit"
        />
      </div>
      <medium-editor
        data-placeholder="Article content"
        :text="articleText"
        v-on:edit="articleTextEdit"
      />
    </div>
  </div>
</template>

<script>
import editor from 'vue2-medium-editor'

export default {
  name: 'app',
  components: {
    'medium-editor': editor
  },
  data: function () {
    return {
      articleText: '',
      articleTitle: ''
    }
  },
  methods: {
    articleTitleEdit: function (operation) {
      this.articleTitle = operation.api.origElements.innerHTML
    },
    articleTextEdit: function (operation) {
      this.articleText = operation.api.origElements.innerHTML
      clearTimeout(this.timeout)
      this.timeout = setTimeout(() => this.save(), 2000)
    },
    save: function () {
      console.log(`saving`)
    }
  }
}
</script>
