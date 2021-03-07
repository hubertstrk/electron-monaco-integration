<template>
  <div id="app" style="width: 100%; height: 100%;">
      <div ref="editor" style="width: 100%; height: 100%;"></div>
  </div>
</template>

<script>
import * as monaco from 'monaco-editor'

export default {
  name: 'App',
  components: {
  },
  mounted () {
    const el = this.$refs.editor
    monaco.editor.create(el, {
      value: ['function x() {', '\tconsole.log("Hello world!");', '}'].join('\n'),
      language: 'markdown'
    })
  }
}
</script>

<style>
</style>
