<template>
  <div id="app">
    <PostContainer />
  </div>
</template>

<script>
import PostContainer from './components/PostContainer.vue'


export default {
  name: 'App',
  components: {
    PostContainer
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
