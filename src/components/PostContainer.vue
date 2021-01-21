<template>
  <div class="posts">
    <h1 class="title">{{ msg }}</h1>
    <div class="inner-hello" v-for="post in posts" v-bind:key="post._id">
   <Post v-bind:post="post" /> 
    </div>
    <p v-if="loading">loading...</p>
  </div>
</template>

<script>
import axios from 'axios';
import Post from './Post.vue'
export default {
  name: 'PostContainer',
  components: {
    Post
  },
  props: {
    msg: String
  },
  data() {
    return {
    posts: [],
    error: Boolean,
    loading: Boolean
    }
  },

      mounted() {
        const url = `https://next.json-generator.com/api/json/get/Vy1Cx2by5`;
        axios
            .get(url)
            .then(response => {
                this.posts = response.data;
                //set state value here , then allow mutation in the input with event emitter ?
            })
            .catch(err => {
                console.error(err);
                this.loading = false;
                this.error = true;
            })
            .finally(() => (this.loading = false));
    }
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.posts {
}
.inner-hello {
background-color:lightgrey;
border: 1px solid black;
margin: 15px 30% 15px 30%;
width:30rem;
padding: 10px;
border-radius: 30px;
}
.title {
color:#c20017;font-size:45px;
}
</style>
