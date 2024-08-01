<template>
        <form class="bg-white" @submit.prevent="handleSubmit">
        <div class="mb-4">
            <label for="name" class="block text-gray-600 font-bold mb-2">Name</label>
            <input type="text" id="name" v-model="name" required class="border-2-solid bg-white border rounded-xl w-full py-2 px-3 text-gray-600 leading-tight focus:outline-none focus:shadow-outline" />
        </div>
        <div class="mb-4">
            <label for="email" class="block text-gray-600 font-bold mb-2">Email</label>
            <input type="email" id="email" v-model="email" required class="border-2-solid bg-white border rounded-xl w-full py-2 px-3 text-gray-600 leading-tight focus:outline-none focus:shadow-outline" />
        </div>
        <div class="mb-4">
            <label for="subject" class="block text-gray-600 font-bold mb-2">Subject</label>
            <input type="text" id="subject" v-model="subject" required class="border-2-solid bg-white border rounded-xl w-full py-2 px-3 text-gray-600 leading-tight focus:outline-none focus:shadow-outline" />
        </div>
        <div class="mb-6">
            <label for="message" class="block text-gray-600 font-bold mb-2">Message</label>
            <textarea id="message" rows="4" v-model="message" required class="border-2-solid bg-white border rounded-xl w-full py-2 px-3 text-gray-600 leading-tight focus:outline-none focus:shadow-outline"></textarea>
        </div>
        <button type="submit" class="bg-green-700 hover:bg-green-900 text-white font-bold py-2 px-4 rounded-xl">
            Submit
        </button>
        </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: '',
        email: '',
        subject: '',
        message: '',
      };
    },
    methods: {
      handleSubmit() {
        // Handle form submission here
        alert('Form submitted!');
        // Replace this with your actual form submission logic
        // e.g., sending data to a server using axios or fetch
      },
    },
  };
  </script>
  