<template>
  <div>
    <h1>{{ msg }}</h1>
    <h1>{{ post.name }}</h1>
    <div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Post',
  props: {
    msg: String,
    post: ['']
  },
  data() {
    return {
    test: 'hello'
    }
  },

}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
