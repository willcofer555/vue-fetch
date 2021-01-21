<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div v-if="posts">
    <li v-for="post in posts" v-bind:key="post.id">Name: {{ post.name.last }} , {{ post.name.first }}, Account Balance: {{ post.balance }}
    </li>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'PostContainer',
  props: {
    msg: String
  },
  data() {
    return {
    posts: []
    }
  },

  async created() {
  try {
  const response = await axios.get(`https://next.json-generator.com/api/json/get/Vy1Cx2by5`)
  this.posts = response.data
  } catch (e){
  this.errors.push(e)
  }
  
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
