<!-- <template>
  <section class="bg-blue-500">
    <div class="container mx-auto flex flex-col lg:flex-row items-center py-12">
      <div class="lg:w-1/2 text-left">
        <h1 class="text-4xl font-bold text-white mb-4">Welcome to Our Website</h1>
        <p class="text-white mb-6">This is a simple hero section with text on the left and an image on the right.</p>
        <button class="bg-white text-blue-500 font-bold py-2 px-4 rounded">Get Started</button>
      </div>
      <div class="lg:w-1/2 mt-6 lg:mt-0">
        <nuxt-img src="https://via.placeholder.com/400" alt="Hero Image" class="w-full rounded-lg shadow-lg"></nuxt-img>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
}
</script>

<style scoped>
/* Add any additional styling here */
</style>
 -->
 <template>
  <section class="h-screen flex px-[16px] items-center">
    <div class="container mx-auto flex flex-col lg:flex-row justify-center items-center py-12">
      <div class="lg:w-1/2 text-left">
        <h1 class="text-4xl font-bold text-gray-600 mb-4">Let's create a savoury and <span class='text-4xl text-green-600 border-4 border-green-600 rounded-full px-4'>cleaner</span> future together</h1>
        <p class="text-gray-400 mb-6">Enabling public awareness of climate issues to safeguard Earth with minimal environmental impact, fostering a sustainable future for generations to come.</p>
        <div class="flex flex-col md:flex-row gap-8">
          <NuxtLink class="bg-white text-green-600 font-bold py-2 px-4 rounded shadow-md" to="/about">Join us Now</NuxtLink>
          <NuxtLink class="bg-white text-green-600 font-bold py-2 px-4 rounded shadow-md" to="/about">Sponser us</NuxtLink>
        </div>
        
      </div>
      <div class="lg:w-1/2 mt-6 lg:mt-0">
        <div class="max-w-full ">
                <AllCard />
            </div>
      </div>
    </div>
  </section>
</template>

<script>


</script>

<style scoped>
/* Add any additional styling here */
</style>
