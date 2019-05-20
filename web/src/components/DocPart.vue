<template>
  <div class="doc-part">
    <h1>{{info.title}}</h1>
    <h2 v-if="info.subtitle">{{info.subtitle}}</h2>
    <doc-file v-for="file in info.files" :type="info.type" :file="'content/' + file" :id="info.title" :key="file"></doc-file>
    <doc-part v-for="part in info.subparts" :info="part" :key="part.title"></doc-part>
  </div>
</template>

<script>
import DocFile from './DocFile.vue'

export default {
  name: 'DocPart',
  props: {
    info: Object
  },
  components: {
    DocFile
  }
}
</script>

<style scoped lang="scss">

</style>
