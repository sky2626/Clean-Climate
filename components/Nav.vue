<template>
    <nav class="bg-white shadow-md fixed w-full z-10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex justify-between h-16">
          <div class="flex">
            <button class="bg-blue-600 text-white px-4 py-2 rounded hidden md:block">Action</button>
          </div>
          <div class="flex items-center space-x-4">
            <div class="hidden md:flex space-x-4">
              <a href="#home" class="text-gray-800 hover:text-blue-600">Home</a>
              <a href="#about" class="text-gray-800 hover:text-blue-600">About</a>
              <a href="#effect" class="text-gray-800 hover:text-blue-600">Effect</a>
              <a href="#solution" class="text-gray-800 hover:text-blue-600">Solution</a>
              <div class="relative">
                <button @click="toggleDropdown" class="text-gray-800 hover:text-blue-600">Resources</button>
                <div v-if="dropdownOpen" class="absolute right-0 mt-2 w-48 bg-white shadow-lg rounded-lg">
                  <a href="#blog" class="block px-4 py-2 text-gray-800 hover:bg-gray-200">Blog</a>
                  <a href="#visit" class="block px-4 py-2 text-gray-800 hover:bg-gray-200">Visit</a>
                </div>
              </div>
            </div>
            <div class="md:hidden flex items-center">
              <button @click="toggleMenu" class="focus:outline-none">
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
                </svg>
              </button>
            </div>
            <div class="flex-shrink-0">
              <img class="h-8 w-8" src="logo.png" alt="Logo">
            </div>
          </div>
        </div>
      </div>
      <div v-if="menuOpen" class="md:hidden">
        <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
          <a href="#home" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Home</a>
          <a href="#about" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">About</a>
          <a href="#effect" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Effect</a>
          <a href="#solution" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Solution</a>
          <div class="relative">
            <button @click="toggleDropdown" class="block w-full text-left px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Resources</button>
            <div v-if="dropdownOpen" class="pl-4">
              <a href="#blog" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Blog</a>
              <a href="#visit" class="block px-3 py-2 rounded-md text-base font-medium text-gray-800 hover:bg-gray-200">Visit</a>
            </div>
          </div>
        </div>
      </div>
    </nav>
  </template>
  
  <script>
  export default {
    data() {
      return {
        menuOpen: false,
        dropdownOpen: false
      }
    },
    methods: {
      toggleMenu() {
        this.menuOpen = !this.menuOpen;
      },
      toggleDropdown() {
        this.dropdownOpen = !this.dropdownOpen;
      }
    }
  }
  </script>
  
  <style scoped>
  /* Add any additional styles here */
  </style>
  