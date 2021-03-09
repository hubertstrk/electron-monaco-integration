<template>
  <div ref="editor" class="editor" />
</template>

<script>
import * as monaco from 'monaco-editor'

export default {
  name: 'editor',
  props: ['value'],
  mounted () {
    const el = this.$refs.editor
    const editor = monaco.editor.create(el, {
      language: "markdown",
      theme: "vs-dark",
      value: this.value,
      automaticLayout: true
    })

    const model = editor.getModel()
    model.onDidChangeContent(e => {
      const value = editor.getModel().getValue()
      this.$emit('input', value)
      console.info(e)
    })
  }
}
</script>

<style lang="css" scoped>
.editor {
  overflow: hidden;
}
</style>
