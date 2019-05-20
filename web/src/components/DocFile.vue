<template>
  <div :id="id" class="doc-file">
    <markdown-file v-if="type == '' || type == undefined || type == 'md' || type == 'markdown'" :file="file"></markdown-file>
    <html-file v-if="type == 'html'" :file="file"></html-file>
  </div>
</template>

<script>
import MarkdownFile from './MarkdownFile.vue'
import HtmlFile from './HtmlFile.vue'

export default {
  name: 'DocFile',
  props: {
    type: String,
    file: String,
    id: String
  },
  components: {
    MarkdownFile,
    HtmlFile
  }
}
</script>

<style lang="scss">
</style>
