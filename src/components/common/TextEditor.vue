<template>
  <medium-editor
      :text="text"
      v-on:edit="processEditOperation"
    >dsfds</medium-editor>
</template>

<script>
import editor from 'vue2-medium-editor'

export default {
  name: 'TextEditor',
  components: {
    'medium-editor': editor
  },
  data: function () {
    return {
      text: ''
    }
  },
  props: {
    msg: String
  },
  methods: {
    processEditOperation: function (operation) {
      this.text = operation.api.origElements.innerHTML
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../../styles/editor.scss";
@import "../../styles/editor-skin.scss";
</style>
