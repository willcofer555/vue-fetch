<template>
  <div class="post">
    <h1>{{ post.name.first }} {{ post.name.last }}</h1>
    <h3> {{ post.email}} </h3>
    <h3> {{ post.address}} </h3>
  </div>
</template>

<script>

export default {
  name: 'Post',
  props: {
    msg: String,
    post: Object
  },
  data() {
    return {
    }
  },

}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.post {
}
</style>
