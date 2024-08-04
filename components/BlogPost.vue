<template>
    <div class="blog-post">
        <img :src="imageUrl" alt="Blog Image" class="w-full h-48 object-cover">
        <div class="p-6">
            <h2 class="text-xl font-bold mb-2">{{ title }}</h2>
            <p class="text-gray-700">{{ description }}</p>
        <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Read More</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'BlogPost',
    props: {
      imageUrl: {
        type: String,
        required: true,
      },
      title: {
        type: String,
        required: true,
      },
      description: {
        type: String,
        required: true,
      },
    },
};
</script>
