<template>
    <div class="flex md:flex-row justify-cneter items-center gap-[18px] ">
        <div class="overflow-hidden flex flex-row max-w-sm bg-gray-100 border border-gray-300 rounded-3xl shadow-lg hover:shadow-xl transition-shadow duration-300 ">
            <div class="p-6">
                <h2 class="text-xl font-bold mb-2 text-gray-600">{{ title }}</h2>
                <p class="text-gray-400">{{ description }}</p>
            </div>
            <img :src="image" alt="Card Image" class="object-cover w-1/3 h-auto shadow-md">
        </div>

    </div>
    
</template>

<script>
  export default {
    name: 'Card',
    props: {
      image: {
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
  