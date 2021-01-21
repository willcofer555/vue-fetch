<template>
  <div class="post">
    <h1> {{ post.name.first }} {{ post.name.last }} </h1>
    <hr>
    <h4> {{ post.email}} </h4>
    <h4> {{ post.phone}} </h4>
  <!--  <h4> {{ post.latitude }}, {{ post.longitude }} </h4> -->
    <h4> {{ post.address }} </h4> 
  </div>
</template>

<script>
/*import store from '../../store/index.js';*/
export default {
  name: 'Post',
  data(){
   return{
    address: String 
    };
  },
  props: {
    post: Object
  },
  methods:{
   updateAddress(){
     console.log(this.post.address)
      } 
  },
  onMount() {
  this.address = this.post.address
  }
}
</script>


<style scoped>
.ml {
margin-left:10px;
}

</style>
