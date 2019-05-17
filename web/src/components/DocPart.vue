<template>
  <div class="doc-part">
    <h1>{{info.title}}</h1>
    <h2 v-if="info.subtitle">{{info.subtitle}}</h2>
    <markdown-file v-for="file in info.files" :file="'content/' + file" :key="file"></markdown-file>
    <doc-part v-for="part in info.subparts" :info="part" :key="part.title"></doc-part>
  </div>
</template>

<script>
import MarkdownFile from './MarkdownFile.vue'

export default {
  name: 'DocPart',
  props: {
    info: Object
  },
  components: {
    MarkdownFile
  }
}
</script>

<style scoped lang="scss">

</style>
