<template>
  <div id="app">
    <doc-header v-if="config.info !== undefined" :title="config.info.title" :client="config.info.subtitle"></doc-header>
    <div class="container" v-if="config.parts !== undefined">
      <doc-part v-for="item in config.parts" :info="item" :key="item.title"></doc-part>
    </div>
  </div>
</template>

<script>
import 'popper.js'
import $ from 'jquery'
import 'bootstrap'

// Components
import DocHeader from './components/DocHeader.vue'
import DocPart from './components/DocPart.vue'

export default {
  name: 'app',
  components: {
    DocHeader,
    DocPart
  },
  data: function () {
    return {
      config: {}
    }
  },
  methods: {
    loadConfig: function () {
      var self = this
      $.get('config.json', function(data) {
        self.$set(self, 'config', data)
      });
    }
  },
  beforeMount: function () {
    this.loadConfig()
  }
}
</script>

<style lang="scss">
@import 'css/reset';
@import "~bootstrap/scss/bootstrap";
@import 'css/default';

body {
  background-color: $color-background;
}

#app {
  font-family: $font-content;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $color-content;
}
</style>
