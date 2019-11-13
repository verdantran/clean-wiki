
<template>
  <div ref="editor"></div>
</template>

<script>
import Quill from 'quill'

export default {
  props: {
    value: {
      type: String,
      required: false,
      default: ''
    },
    placeholder: {
      type: String,
      required: false,
      default: 'Start typing'
    }
  },

  data: function () {
    return {
      editor: null
    }
  },
  mounted () {
    this.editor = new Quill(this.$refs.editor, {
      modules: {
        toolbar: [
          ['bold', 'italic', 'underline', 'strike'], // toggled buttons
          ['blockquote', 'code-block'],
          ['link', 'image']
        ]
      },
      theme: 'bubble',
      formats: ['bold', 'underline', 'header', 'italic'],
      placeholder: this.placeholder
    })

    this.editor.root.innerHTML = this.value

    this.editor.on('text-change', () => this.update())
  },

  methods: {
    update () {
      this.$emit(
        'input',
        this.editor.getText() ? this.editor.root.innerHTML : ''
      )
    }
  }
}
</script>
