<template>
    <article class="max-w-4xl my-6 mx-auto  bg-white rounded-lg shadow-md scroll-down">
      <img :src="image" alt="Blog post image" class="w-full h-64 object-cover bg-animate rounded-t-lg mb-4">
      <div class="p-6">
        <h2 class="text-2xl font-bold text-gray-600 mb-2">{{ title }}</h2>
        <p class="text-gray-600 mb-4 ">{{ date }}</p>
        <div class="p-1" v-html="content"></div>
      </div>
      
    </article>
  </template>
  
  <script>
  export default {
    props: {
      title: {
        type: String,
        required: true
      },
      date: {
        type: String,
        required: true
      },
      content: {
        type: String,
        required: true
      },
      image: {
        type: String,
        required: true
      }
    }
  }
  </script>

<style>

.scroll-down {
        cursor: pointer;
        transition: all 0.3s ease-in-out;
    }

.scroll-down:hover {
    transform: translateY(5px);
}
.bg-animate {
  /* Initial state (hidden) */
    opacity: 0;
    transform: translateY(20px); /* Add some vertical offset */

  /* Animation properties */
    animation: text-animation 1s ease-in-out forwards;
}

@keyframes bg-animation {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}


    .text-animate {
  /* Initial state (hidden) */
    opacity: 0;
    transform: translateY(20px); /* Add some vertical offset */

  /* Animation properties */
    animation: text-animation 1s ease-in-out forwards;
}

@keyframes text-animation {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}


</style>