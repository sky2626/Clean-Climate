<template>
    <nav class="bg-white shadow-md">
      <div class="container mx-auto px-4 pt-4 pb-2 flex justify-between items-center">
        <!-- Logo -->
        <div class="text-2xl font-bold">
          <NuxtLink to="/">
                    <img src="/logo-2.png" alt="logo img" hight="" width="">
            </NuxtLink>
        </div>
        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-6">
          <NuxtLink to="/" class="hover:text-green-800 font-semibold text-green-600">Home</NuxtLink>
          <NuxtLink to="/about" class="hover:text-green-800 font-semibold text-green-600">About</NuxtLink>
          <NuxtLink to="/solutions" class="hover:text-green-800 font-semibold text-green-600">Solutions</NuxtLink>
          <NuxtLink to="/effects" class="hover:text-greeen-800 font-semibold text-green-600">Effects</NuxtLink>
                <div class="relative inline-block text-left">
                    <UDropdown class="shadow-lg" :items="dropdownItems" :popper="{ placement: 'bottom-start' }">
                        <UButton color="primary" labelclass="text-green-400" label="Resources" trailing-icon="i-heroicons-chevron-down-20-solid" />
                    </UDropdown>
                </div>
            </div>
    
        <!-- Mobile Menu Button -->
        <div class="md:hidden">
          <button class="haver:bg-" @click="drawer">
            <svg 
              class="h-8 w-8 fill-current text-black"
              fill="none" stroke-linecap="round" 
              stroke-linejoin="round" stroke-width="2" 
              viewBox="0 0 24 24" stroke="currentColor">
                <path d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
          </button>
        </div>
      
      <!-- Mobile Menu -->
      <transition name="slide">
        <div v-if="isMenuOpen" class="lg:hidden fixed inset-0 bg-white z-50 p-4">
          <button @click="toggleMenu" class="focus:outline-none mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
          <NuxtLink to="/" class="block py-2 px-4 text-sm hover:bg-gray-200">Home</NuxtLink>
          <NuxtLink to="/about" class="block py-2 px-4 text-sm hover:bg-gray-200">About</NuxtLink>
          <NuxtLink to="/solutions" class="block py-2 px-4 text-sm hover:bg-gray-200">Solutions</NuxtLink>
          <NuxtLink to="/effects" class="block py-2 px-4 text-sm hover:bg-gray-200">Effects</NuxtLink>
          <div class="relative group">
            <NuxtLink to="#" class="block py-2 px-4 text-sm hover:bg-gray-200">Resources</NuxtLink>
            <div class="pl-4">
              <NuxtLink to="/resources/stimulation" class="block py-2 px-4 text-sm hover:bg-gray-200">Stimulation</NuxtLink>
              <NuxtLink to="/resources/articles" class="block py-2 px-4 text-sm hover:bg-gray-200">Articles</NuxtLink>
              <NuxtLink to="/resources/tags" class="block py-2 px-4 text-sm hover:bg-gray-200">Tags</NuxtLink>
            </div>
          </div>
        </div>

        </transition>
    </div>
    </nav>
  </template>
  
  <script>
  export default {
    data() {
    return {
      dropdownItems: [
        [{ label: 'Climate Stimulation', to: 'https://climatekids.nasa.gov/' }],
        [{ label: 'Blog', to: '/blog' }]
      ]
    }
  },
    methods: {
        toggleDropdown() {
        this.isOpen = !this.isOpen;
    },
        drawer() {
            this.isOpen = !this.isOpen;
        },
  },
}
</script>
  
<style scoped>
  .slide-enter-active, .slide-leave-active {
    transition: transform 0.3s ease;
}
  .slide-enter, .slide-leave-to {
    transform: translateX(-50%);
  }
</style>  