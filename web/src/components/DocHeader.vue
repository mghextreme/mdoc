<template>
  <div class="doc-header jumbotron jumbotron-fluid">
    <div class="container">
      <h1>{{title}}</h1>
      <h3>{{client}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DocHeader',
  props: {
    title: String,
    client: String,
    date: String
  }
}
</script>

<style scoped lang="scss">

</style>
