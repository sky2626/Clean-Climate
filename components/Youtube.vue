<template>
    <div class="max-w-4xl mx-auto p-6 bg-white rounded-lg shadow-md">
      <div v-if="videoId" class="aspect-w-16 aspect-h-9">
        <iframe
          :src="`https://www.youtube.com/embed/${videoId}`"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
          class="w-full h-full rounded-lg"
        ></iframe>
      </div>
      <div v-else class="text-center text-gray-700">
        Loading video...
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      videoId: {
        type: String,
        required: true
      }
    }
  }
  </script>
  
