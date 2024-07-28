<template>
    <div class="flex md:flex-row justify-cneter items-center gap-[18px] ">
        <div class="flex flex-row bg-gray-100 rounded-[40px]">
            <div class="px-24 py-[48px]">
                <h2 class="text-xl font-bold text-gray-600">{{ title }}</h2>
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
