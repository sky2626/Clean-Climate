<script setup lang="ts">
import AllCard from '~/components/AllCard.vue';
import BlogPostsHome from '~/components/BlogPostsHome.vue';
</script>

<template>
    <div class="bg-white screen ">
        <div class=" bg-white screen">
            <HeroSection />
        </div>
        
        <div class="px-[18px] my-[200px] gap-[18px] flex flex-col md:flex-row justify-center" >
            <Card 
                image="/bulb.png"
                title="Afforestation Impact on the environment"
                description="This is the description for card 2."
            />
            <Card 
                image="/co2.png"
                title="Impact of carbon monoxide"
                description="This is the description for card 2."
            />
        </div>
        <div>
            <div class="px-[18px] gap-[8px] flex justify-center items-center flex-col mt-24" >
                <h1 class="text-gray-600 text-4xl font-extrabold text-center">
                    Let's make our Climate <span>cleaner & sustainable</span>
                </h1>
                <p class="text-gray-400 text-center md:w-[600px]">
                    Collective responsibility that requires efforts from individuals, communities, businesses, and governments.
                </p class="mt-2">
                <Button> Learn More </Button>
            </div>
        </div>
        <div class="flex flex-col md:flex-row justify-center items-center gap-[18px] mt-24 mx-[18px]">
            <h2 class="text-xl bg-[#e9fbc9] rounded-[40px] px-36 md:px-24 py-[48px] font-bold text-[#486415]">We</h2>
            <h2 class="text-xl bg-[#3c487d] rounded-[40px] px-36 md:px-24 py-[48px] font-bold text-[#c9d2fb]">Protect</h2>
            <div class="flex bg-[#fbdfc9] rounded-[40px] px-36 md:px-24 py-[48px] justify-center">
                <img src="/arrow.svg" alt="arrow image">
            </div>
            <h2 class="text-xl bg-[#c9fbf9] rounded-[40px] px-36 md:px-24 py-[48px] font-bold text-[#185755]">Nature</h2>
            
        </div>
        <div class="flex flex-col md:flex-row px-[18px] md:px-[450px] justify-center items-center md:justify-between mt-[50px]">
            <h1 class="text-gray-600 text-4xl font-extrabold text-center md:text-start">Our initiatives for the 2024</h1>
            <p class="text-gray-400 text-center md:text-end w-[300px]">Find out the projects that we are undertaking this year.</p>
        </div>
        <div class="mx-[18px] md:mx-[430px] mt[50px] mb-[100px]"> 
            
            <Mytable />
        </div>
        <div class="flex justify-center items-center mx-[18px] md:mx-[320px] rounded-lg shadow-xl flex-col md:flex-row gap-8  ">
            <div class="max-w-[600px]">
                <AllCard />
            </div>
            <div clss="p-[18px] ">
                <h1 class="text-3xl text-gray-600 font-bold text-black">What is Climate Change</h1>
                <p class="text-gray-400">long-term alterations in the average weather patterns on Earth. 
                    While the Earth's climate has always changed over geological time, 
                    recent decades have seen a significant increase in the rate of change, 
                    largely due to human activities.
                </p>
            </div>
        </div>

        <div>
            
            <UContainer>
                <Placeholder class="h-32" />
                <div class="mt-[100px]">
                    <h1 class='text-3xl text-gray-600 font-bold'>Latest Update</h1>
                    <hr>
                    <div>
                        <BlogPostsHome />
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
