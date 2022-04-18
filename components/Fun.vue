<template>
  <h1 class="red">Hello {{ slug }}!</h1>
</template>

<script>
  export default {
      name: 'Fun',
      data () {
          return {
              slug: 'teste'
          }
      }
  }
</script>

<style>
  .red {
    color: red;
  }
</style>