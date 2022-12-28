<script>

import sourceData from '../data.json'

export default {
  data () {
    return {
      threads: sourceData.threads
    }
  }
}

</script>

<template>
  <h1>Hi</h1>

  <div>{{threads}}</div>

</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
