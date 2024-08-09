<script setup lang="ts">
import AllCard from '~/components/AllCard.vue';
import BlogPostsHome from '~/components/BlogPostsHome.vue';
</script>

<template>
    <div class="bg-white screen ">
        <HeroSection />
        
        <div class="flex justify-center items-center flex-col  px-4 md:px-8">
            <h1 class="text-gray-600 text-4xl font-extrabold text-center">
            Let's make our Climate <span>cleaner & sustainable</span>
            </h1>
            <p class="text-gray-400 text-center mt-2 md:w-3/4 lg:w-1/2">
            Collective responsibility that requires efforts from individuals, communities, businesses, and governments.
            </p>
            <NuxtLink class="mt-4 py-4 px-16 text-white bg-green-600 rounded-full font-semibold" to="/solutions">Learn more</NuxtLink>
            
        </div>
        <UContainer>
                <div class="grid grid-cols-2 md:grid-cols-4 items-center gap-4 mt-24 mx-4 md:mx-8">
                    <h2 class="text-xl bg-[#e9fbc9] text-center rounded-full px-8 md:px-24 py-12 font-bold text-[#486415]">We</h2>
                    <h2 class="text-xl bg-[#3c487d] text-center  rounded-full px-8 md:px-24 py-12 font-bold text-[#c9d2fb]">Protect</h2>
                    <div class="flex bg-[#fbdfc9] rounded-full px-8 md:px-24 py-12 justify-center">
                        <img src="/arrow.svg" alt="arrow image" class="w-10 h-10">
                    </div>
                    <h2 class="text-xl bg-[#c9fbf9] text-center  rounded-full px-8 md:px-24 py-12 font-bold text-[#185755]">Nature</h2>
                </div>
        </UContainer>
        
        <div class="flex flex-col md:flex-row px-[18px] md:px-[450px] justify-center items-center md:justify-between mt-[50px]">
            <h1 class="text-gray-600 text-4xl font-extrabold text-center md:text-start text-animate">Our initiatives for the 2024</h1>
            <p class="text-gray-400 text-center md:text-end w-[300px] text-animate">Find out the projects that we are undertaking this year.</p>
        </div>
        <div class="mx-[18px] md:mx-[430px] mt[50px] mb-[100px] scroll-down"> 
            
            <Mytable />
        </div>
        <UContainer>
            <div class="flex flex-col md:flex-row justify-center items-center rounded-lg shadow-xl gap-8 p-4 scroll-down">
            <div class="max-w-full md:max-w-[600px]">
                <AllCard />
            </div>
            <div class="p-4 scrow-down">
                <h1 class="text-3xl font-bold text-gray-600 text-animate">What is Climate Change</h1>
                <p class="text-gray-400 mt-2 text-animate">
                    Long-term alterations in the average weather patterns on Earth. While the Earth's climate has always changed over geological time, recent decades have seen a significant increase in the rate of change, largely due to human activities.
                </p>
            </div>
        </div>
        </UContainer>
        

        <div>
            
            <UContainer>
                <Placeholder class="h-32" />
                <div class="mt-[100px]">
                    <h1 class='text-3xl text-gray-600 font-bold text-animate'>Latest Update</h1>
                    <hr>
                    <div class="flex justify-center flex-row md:flex-col items-center">
                        <BlogPostsHome />
                        <div class="text-lg text-green-600 font-semibold text-semibold px-2 rounded-lg hover:bg-green-600 hover:text-white">
                            <NuxtLink  to="/blog">Read More</NuxtLink>
                        </div>
                    </div>
                </div>  
                <div>  
                    <!-- <Youtube :videoId="videoId" /> -->
                </div>
            </UContainer>
            
        </div>
    </div>
</template>

<!-- <script>
import Youtube from './components/Youtube.vue'

export default {
  components: {
    Youtube
  },
  data() {
    return {
      videoId: ''
    }
  },
  async mounted() {
    try {
      const response = await fetch(`https://www.googleapis.com/youtube/v3/videos?id=YOUR_VIDEO_ID&key=YOUR_API_KEY&part=snippet,contentDetails,statistics,status`);
      const data = await response.json();
      if (data.items && data.items.length > 0) {
        this.videoId = data.items[0].id;
      }
    } catch (error) {
      console.error('Error fetching YouTube video:', error);
    }
  }
}
</script>
 -->
<style>


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