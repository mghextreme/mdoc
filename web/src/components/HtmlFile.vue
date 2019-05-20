<template>
  <div class="html-file content"></div>
</template>

<script>
import $ from 'jquery';

export default {
  name: 'HtmlFile',
  props: {
    file: String
  },
  computed: {
    filePath: function () {
      if (this.file[0] === '/')
        return this.file
      else
        return '/' + this.file
    },
    pageUrl: function () {
      return window.location.protocol + "//" + window.location.host
    }
  },
  methods: {
    loadContent: function () {
      $(this.$el).load(this.pageUrl + this.filePath)
    }
  },
  mounted: function () {
    this.loadContent()
  }
}
</script>

<style lang="scss">

</style>
