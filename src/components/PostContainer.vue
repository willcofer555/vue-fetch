<template>
  <div class="posts">
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


<style scoped>
.posts {
}
.inner-hello {
border: 1px solid black;
margin: 15px 30% 15px 30%;
width:30rem;
padding: 10px 0 15px 0;
border-radius: 30px;
background-color: #003366;
color: white;
box-shadow:         3px 3px 5px 6px #ccc;
}
.title {
color:#c20017;font-size:45px;
}
</style>
