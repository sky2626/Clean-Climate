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
  <section class="h-screen flex mx-4">
    <div class="container mx-auto flex flex-col lg:flex-row items-center pb-12">
      <div class="md:w-1/2 text-left">
        <h1 class="text-4xl text-center md:text-start font-bold text-gray-600 mb-4 text-animate">Let's create a savoury and <span class='text-4xl text-green-600 border-4 border-green-600 rounded-full px-4'>cleaner</span> future together</h1>
        <p class="text-gray-400 text-center md:text-start mb-6 text-animate">Enabling public awareness of climate issues to safeguard Earth with minimal environmental impact, fostering a sustainable future for generations to come.</p>
        <div class="flex flex-col md:flex-row gap-2 md:gap-8">
          <NuxtLink class="bg-white text-center text-green-600 font-bold py-2 px-4 rounded shadow-md scroll-down" to="/about">Join us</NuxtLink>
         
        </div>
        
      </div>
      <div class="lg:w-1/2 mt-6 lg:mt-0">
        <div class="max-w-full bg-animate ">
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

.scroll-down {
        cursor: pointer;
        transition: all 0.3s ease-in-out;
    }

.scroll-down:hover {
    transform: translateY(5px);
}
.bg-animate {
  /* Initial state (hidden) */
    opacity: 0;
    transform: translateY(20px); /* Add some vertical offset */

  /* Animation properties */
    animation: text-animation 1s ease-in-out forwards;
}

@keyframes bg-animation {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}


    .text-animate {
  /* Initial state (hidden) */
    opacity: 0;
    transform: translateY(20px); /* Add some vertical offset */

  /* Animation properties */
    animation: text-animation 1s ease-in-out forwards;
}

@keyframes text-animation {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

</style>
