<template>
  <editor style="editor" :value="text" @event="onTextChanged" />
</template>

<script>
import editor from './editor'

export default {
  name: 'App',
  components: {
    editor
  },
  data () {
    return {
      text: "# heading 1"
    }
  },
  methods: {
    onTextChanged (text) {
      console.log(text)
    }
  }
}
</script>

<style scoped lang="css">
.editor {
  height: 100%;
  width: 100%;
}
</style>
