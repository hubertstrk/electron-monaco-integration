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
  methods: {
    textChanged (e) {
      console.log(e)
    }
  },
  mounted () {
    const el = this.$refs.editor
    const editor = monaco.editor.create(el)
    // const model = monaco.editor.createModel('foo', 'markdown', monaco.Uri)


    editor.onDidChangeModelContent((e) => {
      console.log(e)
    })
    editor.getModel().onDidChangeContent((e) => {
      const value = editor.getModel().getValue()
      console.log(`${value}, ${e}`)
    })
    // const model1 = monaco.editor.getModel(monaco.Uri)
    console.log(editor)
  }
}
</script>

<style>
</style>
