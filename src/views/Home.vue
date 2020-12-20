<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error">{{error}}</div>
    <div v-if="posts.length">
      <PostList v-if="showPosts" :posts="posts" />
    </div>
    <div v-else>
      loading ...
    </div>
    
  </div>
</template>

<script>
import getPosts from '../composables/getPosts'
import PostList from '../components/PostList'

export default {
  name: 'Home',
  components:{
    PostList
  },
  setup(){
    const showPosts = true
    const {posts, error, load} = getPosts()
    load()
    return {posts,showPosts,error}

  }
}
  
</script>
