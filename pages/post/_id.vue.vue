<!-- pages/post/_id.vue -->
<template>
    <div>
      <h1>{{ post.title }}</h1>
      <img :src="post.image" alt="Post Image">
      <p v-html="post.content"></p>
    </div>
  </template>
  
  <script>
  export default {
    async asyncData({ params }) {
      // Fetch the post data based on the ID
      const post = await fetchPostById(params.id)
      return { post }
    }
  }
  </script>
  