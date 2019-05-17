<template>
  <div class="markdown-file content"></div>
</template>

<script>
import markdownIntoHtml from 'markdown-into-html';

export default {
  name: 'MarkdownFile',
  props: {
    file: String
  },
  computed: {
    filePath: function () {
      if (this.file[0] === '/')
        return this.file;
      else
        return '/' + this.file;
    },
    pageUrl: function () {
      return window.location.protocol + "//" + window.location.host
    }
  },
  methods: {
    loadContent: async function () {
      var htmlContent = await markdownIntoHtml({
        url: this.pageUrl + this.filePath
      })
      this.$el.innerHTML = htmlContent
    }
  },
  created: function () {
    this.loadContent()
  }
}
</script>

<style lang="scss">
.markdown-file {
  h1:first-of-type {
    display: none;
  }
}
</style>
