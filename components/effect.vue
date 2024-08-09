<template>
    <div class="container mx-auto p-4">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
        <div v-for="item in paginatedItems" :key="item.id" class="bg-white p-4 rounded-lg shadow-md">
          <img :src="item.image" alt="Item Image" class="w-full h-48 object-cover rounded-lg mb-4">
          <h2 class="text-xl font-bold text-gray-600">{{ item.title }}</h2>
          <p>{{ item.description }}</p>
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
          { id: 1, title: 'Item 1', description: 'Description for item 1', image: 'https://via.placeholder.com/400' },
          { id: 2, title: 'Item 2', description: 'Description for item 2', image: 'https://via.placeholder.com/400' },
          { id: 3, title: 'Item 3', description: 'Description for item 3', image: 'https://via.placeholder.com/400' },
          { id: 4, title: 'Item 4', description: 'Description for item 4', image: 'https://via.placeholder.com/400' },
          { id: 5, title: 'Item 5', description: 'Description for item 5', image: 'https://via.placeholder.com/400' },
          { id: 6, title: 'Item 6', description: 'Description for item 6', image: 'https://via.placeholder.com/400' },
          { id: 7, title: 'Item 7', description: 'Description for item 7', image: 'https://via.placeholder.com/400' },
          { id: 8, title: 'Item 8', description: 'Description for item 8', image: 'https://via.placeholder.com/400' },
          { id: 9, title: 'Item 9', description: 'Description for item 9', image: 'https://via.placeholder.com/400' },
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
