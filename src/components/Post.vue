<template>
  <div class="post">
  <table>

  </table>
    <h1> {{ post.name.first }} {{ post.name.last }} </h1>
    <h4> {{ post.email}} </h4>
    <h4> {{ post.latitude }}, {{ post.longitude }} </h4>
    <h4> {{ post.address }} </h4>
  </div>
</template>

<script>

export default {
  name: 'Post',
  props: {
    post: Object
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
