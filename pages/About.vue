<script setup lang="ts">
import ContactForms from '~/components/ContactForms.vue';
</script>

<template>
    <div>
        <UContainer>
            <div class="container mx-auto py-12">
            <h1 class="text-3xl font-bold text-gray-600 text-center my-[100px]">About Us</h1>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div>
                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Our Mission</h2>
                    <p class="text-gray-600">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.   
                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                    </p>

                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Our Team</h2>
                </div>

                <div>
                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Our Impact</h2>
                    <p class="text-gray-600">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.   
                    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
                    </p>

                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Partners</h2>
                </div>
            </div>
            <div class="flex flex-col md:flex-row gap-[40px] mt-[100px]">
                <div class="text-gray-600  w-1/2">
                    <h2 class="text-2xl font-bold mb-4 ">Contact Us</h2>
                    <p>Email: info@cleanclimate.com</p>
                    <p>Phone: +1234567890</p>
                </div>
                <ContactForms class="w-auto md:w-1/2" />
            </div>
            
            </div>
        </UContainer>
        
    </div>
</template>