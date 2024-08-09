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
          { id: 1, title: 'Carbon Dioxide (CO2)', description: 'CO2 is responsible for approximately three-quarters of global greenhouse gas emissions. It is released through various human activities, primarily the burning of fossil fuels such as coal, oil, and natural gas for energy, transportation, and industrial processes. Power plants, automobiles, and factories are significant contributors. CO2 is also released during deforestation, as trees that absorb CO2 are cut down.', image: 'https://cdn.pixabay.com/photo/2024/01/31/19/56/ai-generated-8544748_1280.jpg' },
          { id: 2, title: 'Deforestation', description: "Forests play a critical role in regulating the Earth's climate by absorbing CO2 from the atmosphere during photosynthesis. Deforestation, which involves clearing forests for agriculture, logging, or urban development, reduces the planet's capacity to absorb CO2. This loss of trees contributes to higher atmospheric CO2 levels. Deforestation also disrupts local ecosystems, leading to biodiversity loss and altering the water cycle, which can exacerbate climate change impacts.", image: 'https://cdn.pixabay.com/photo/2022/02/13/17/34/wood-7011677_1280.jpg' },
          { id: 3, title: 'Chemical Manufacturing', description: "The chemical industry is another major source of GHG emissions. The production of chemicals, including fertilizers, plastics, and other industrial products, often involves energy-intensive processes that release CO2, methane, and other pollutants. Additionally, certain chemical processes produce nitrous oxide and other greenhouse gases as byproducts.", image: 'https://cdn.pixabay.com/photo/2013/03/13/20/44/netherlands-93274_1280.jpg' },
          { id: 4, title: 'Fertilizer Use', description: "The use of synthetic nitrogen-based fertilizers in agriculture increases the amount of nitrogen in the soil, which can be converted to nitrous oxide by soil bacteria. This process, known as nitrification and denitrification, is a significant source of N2O emissions. As global food production increases to meet the demands of a growing population, fertilizer use is expected to rise, contributing to higher nitrous oxide emissions.", image: 'https://cdn.pixabay.com/photo/2020/05/21/15/38/fertilizer-5201380_1280.jpg' },
          { id: 5, title: 'Road Transprots', description: "The transportation sector is a major source of CO2 emissions, with road transport accounting for the largest share. Cars, trucks, and buses that run on gasoline and diesel fuel release significant amounts of CO2. As urbanization and economic development increase, the number of vehicles on the road continues to grow, contributing to higher emissions.", image: 'https://cdn.pixabay.com/photo/2014/04/02/16/18/car-306868_960_720.png' },
          { id: 6, title: 'Burning Fossil Fuels for Electricity', description: "The generation of electricity from fossil fuels, such as coal, natural gas, and oil, is the largest single source of CO2 emissions worldwide. Power plants that burn these fuels release vast quantities of CO2 into the atmosphere. Coal-fired power plants are particularly carbon-intensive, and despite efforts to transition to renewable energy sources, fossil fuels still dominate global energy production.", image: 'https://cdn.pixabay.com/photo/2010/12/16/14/44/fire-3593_1280.jpg' },
          { id: 7, title: 'Waste Incineration', description: "The incineration of waste, particularly plastics and other carbon-based materials, releases CO2 and other pollutants into the atmosphere. While waste-to-energy plants can generate electricity from burning waste, they also contribute to greenhouse gas emissions. The environmental impact of waste incineration depends on the composition of the waste and the efficiency of the incineration process.", image: 'https://cdn.pixabay.com/photo/2016/11/21/15/42/disposal-1846033_1280.jpg' },
          { id: 8, title: 'Urban Heat Islands', description: "Urban areas tend to be warmer than surrounding rural areas due to human activities and the concentration of heat-absorbing materials like concrete, asphalt, and buildings. This phenomenon, known as the urban heat island effect, can increase energy demand for cooling, thereby raising CO2 emissions. Urbanization also leads to the loss of green spaces, which can exacerbate the effects of climate change.", image: 'https://cdn.pixabay.com/photo/2015/09/12/00/46/buildings-936589_1280.jpg' },
          { id: 9, title: 'Increased Energy Demand', description: "Urbanization drives higher energy demand for heating, cooling, lighting, and transportation. As more people move to cities and urban areas expand, the demand for electricity and fuel increases, leading to higher greenhouse gas emissions. The construction of new buildings and infrastructure further contributes to emissions through the use of energy-intensive materials and processes.", image: 'https://cdn.pixabay.com/photo/2018/01/05/07/16/person-3062271_1280.jpg' },
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
