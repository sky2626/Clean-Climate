<script setup lang="ts">
const items = [
  'https://cdn.pixabay.com/photo/2014/07/30/02/00/iceberg-404966_1280.jpg',
  'https://fastly.picsum.photos/id/162/1500/998.jpg?hmac=j-Xr1aKHzCJQigPBLF0nKTudXM2w9u1-Smxlam0YOt8',
  'https://fastly.picsum.photos/id/222/1800/977.jpg?hmac=pd-vkWA544ktuiSTDnx0Btezs9lMx99cvCU4KVzFBmI',
  'https://fastly.picsum.photos/id/475/4288/2848.jpg?hmac=04kbAs78mTA8qt-g4RoGd_oI6Qzc-4WmvqBQ6fjcR0s',
  'https://cdn.pixabay.com/photo/2023/09/19/17/51/factory-8263188_1280.jpg',
  'https://cdn.pixabay.com/photo/2022/04/12/04/46/climate-change-7127153_1280.jpg'
]

const carouselRef = ref()

onMounted(() => {
  setInterval(() => {
    if (!carouselRef.value) return

    if (carouselRef.value.page === carouselRef.value.pages) {
      return carouselRef.value.select(0)
    }

    carouselRef.value.next()
  }, 3000)
})
</script>

<template>
  <UCarousel
    ref="carouselRef"
    v-slot="{ item }"
    :items="items"
    :ui="{ item: 'basis-full' }"
    class="rounded-lg overflow-hidden"
    indicators
  >
    <img :src="item" class="w-full" draggable="false">
  </UCarousel>
</template>

