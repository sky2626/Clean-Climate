<template>
    <div class="container mx-auto p-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div v-for="item in paginatedItems" :key="item.id" class="bg-white p-4 rounded-lg shadow-md">
          <img :src="item.image" alt="Item Image" class="w-full h-48 object-cover rounded-lg mb-4">
          <h2 class="text-xl font-bold text-gray-600">{{ item.title }}</h2>
          <p class="text-gray-400">{{ item.description }}</p>
          <button @click="openModal(item)" class="mt-2 bg-green-600 text-white py-2 px-4 rounded">View More</button>
        </div>
      </div>
      <div class="flex justify-center mt-4">
        <button @click="prevPage" :disabled="currentPage === 1" class="px-4 py-2 mx-1 bg-green-600 rounded">Previous</button>
        <button v-for="page in totalPages" :key="page" @click="goToPage(page)" :class="{'bg-green-600 text-white': currentPage === page, 'bg-gray-300': currentPage !== page}" class="px-4 py-2 mx-1 rounded">{{ page }}</button>
        <button @click="nextPage" :disabled="currentPage === totalPages" class="px-4 py-2 mx-1 bg-green-600 rounded">Next</button>
      </div>
  
      <!-- Modal -->
      <transition name="fade">
        <div v-if="isModalOpen" class="fixed inset-0 bg-gray-800 bg-opacity-75 flex items-center justify-center z-50">
          <div class="bg-white p-6 rounded-lg shadow-lg max-w-lg w-full">
            <img :src="selectedItem.image" alt="Selected Item Image" class="w-full h-48 object-cover rounded-lg mb-4">
            <h2 class="text-2xl text-gray-600 font-bold mb-4">{{ selectedItem.title }}</h2>
            <p class="text-gray-400">{{ selectedItem.description }}</p>
            <button @click="closeModal" class="mt-4 bg-red-500 text-white py-2 px-4 rounded">Close</button>
          </div>
        </div>
      </transition>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          { id: 1, title: 'Transition to Renewable Energy', description: 'Replace fossil fuels with renewable energy sources such as solar, wind, hydroelectric, and geothermal power.', image: 'https://cdn.pixabay.com/photo/2017/09/12/13/21/photovoltaic-system-2742302_1280.jpg' },
          { id: 2, title: 'Reforestation and Afforestation', description: 'Plant trees on degraded land and restore forests. Afforestation involves planting trees on land that has not previously been forested.', image: 'https://cdn.pixabay.com/photo/2023/06/22/07/13/soil-8080788_1280.jpg' },
          { id: 3, title: 'Green Manufacturing', description: 'Adopt cleaner production technologies and processes that reduce emissions in industries like cement, steel, and chemicals.', image: 'https://cdn.pixabay.com/photo/2017/10/23/14/19/machine-2881168_1280.jpg' },
          { id: 4, title: 'Climate-Smart Agriculture', description: 'Implement farming practices that increase productivity while reducing emissions, such as precision agriculture, optimized fertilizer use, and improved livestock management.', image: 'https://cdn.pixabay.com/photo/2020/06/23/06/45/dji-5331570_960_720.jpg' },
          { id: 5, title: 'Electrification of Transport', description: 'Transition to electric vehicles (EVs) and invest in public transportation powered by renewable energy.', image: 'https://cdn.pixabay.com/photo/2022/02/24/08/43/bus-7032023_960_720.jpg' },
          { id: 6, title: 'Transition to Renewable Energy', description: 'Expand the deployment of renewable energy sources, such as solar and wind, in the electricity grid.', image: 'https://cdn.pixabay.com/photo/2022/07/24/17/55/wind-energy-7342177_1280.jpg' },
          { id: 7, title: 'Reduce, Reuse, Recycle', description: 'Encourage waste reduction at the source, increase recycling rates, and promote the reuse of materials.', image: 'https://cdn.pixabay.com/photo/2014/01/03/01/54/recycle-237874_960_720.jpg' },
          { id: 8, title: 'Green Infrastructure', description: 'Develop urban green spaces, green roofs, and urban forests to combat the urban heat island effect and absorb CO2.', image: 'https://cdn.pixabay.com/photo/2016/11/18/22/31/architecture-1837176_960_720.jpg' },
          { id: 9, title: 'International Cooperation', description: 'Countries must work together under frameworks like the Paris Agreement to set and meet ambitious climate targets. Sharing technology, knowledge, and financial resources is key to addressing global climate change.', image: 'https://cdn.pixabay.com/photo/2016/08/09/10/25/earth-1580260_1280.jpg' },
        ],
        currentPage: 1,
        itemsPerPage: 3,
        isModalOpen: false,
        selectedItem: {},
      }
    },
    computed: {
      totalPages() {
        return Math.ceil(this.items.length / this.itemsPerPage);
      },
      paginatedItems() {
        const start = (this.currentPage - 1) * this.itemsPerPage;
        const end = start + this.itemsPerPage;
        return this.items.slice(start, end);
      }
    },
    methods: {
      openModal(item) {
        this.selectedItem = item;
        this.isModalOpen = true;
      },
      closeModal() {
        this.isModalOpen = false;
      },
      prevPage() {
        if (this.currentPage > 1) {
          this.currentPage--;
        }
      },
      nextPage() {
        if (this.currentPage < this.totalPages) {
          this.currentPage++;
        }
      },
      goToPage(page) {
        this.currentPage = page;
      }
    }
  }
  </script>
  
  <style scoped>
  .fade-enter-active, .fade-leave-active {
    transition: opacity 0.5s;
  }
  .fade-enter, .fade-leave-to {
    opacity: 0;
  }
  </style>
  