<template>
    <div class="flex md:flex-row justify-cneter items-center gap-[18px] ">
        <div class="flex flex-row bg-gray-100 rounded-3xl">
            <div class="p-6">
                <h2 class="text-xl font-bold mb-2 text-gray-600">{{ title }}</h2>
            </div>
        </div>

    </div>
    
</template>

<script>
  export default {
    name: 'Card',
    props: {
      title: {
        type: String,
        required: true,
      },
    },
    
};
</script>
