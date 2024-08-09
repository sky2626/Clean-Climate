
<template>
    <div>
        <div class="flex justify-center items-center">
            <div class="back w-[1400px] h-[300px] flex justify-center items-center flex-col rounded-xl mx-[18px]">
                <h1 class="text-3xl font-bold text-white text-center text-animate ">About Us</h1>
                <p class="text-center text-white text-animate">What we do</p>
            </div>
        </div>
        
        <UContainer>
            <div class="container mx-auto pb-12 pt-[200px]">
            

            <div class="grid grid-cols-1 gap-[200px] ">
                <div class="flex grid grid-cols-1 md:grid-cols-2 gap-8 items-center scroll-down shadow-lg rounded-lg">
                    <img class="rounded-3xl" src="/public/bg.jpg" alt="">
                    <div class="p-8">
                        <h2 class="text-2xl text-gray-600 font-bold mb-4 text-animate">Our Mission</h2>
                        <p class="text-gray-600 text-animate">
                        Unlocking Climate Knowledge for a Resilient Tomorrow: Empowering individuals and communities 
                        through climate education and awareness, facilitating informed decision-making, adaptive resilience, 
                        and sustainable development for a climate-resilient future.
                        </p>
                    </div>
                </div>

                <div class="flex grid grid-cols-1 md:grid-cols-2 gap-8 items-center scroll-down shadow-lg rounded-lg">
                    <img class="rounded-3xl md:order-last" src="/public/one.jpg" alt="">
                    <div class="p-8">
                        <h2 class="text-2xl text-gray-600 font-bold mb-4 text-animate">Our Impact</h2>
                        <p class="text-gray-600 text-animate">
                        Here at Clean Climate, we are committed to creating a sustainable future through education and awareness. 
                        Since our inception in 2024, we have been dedicated to empowering individuals and communities to make informed decisions for a 
                        climate-resilient world. Join us in making a real difference.
                        </p>
                    </div>
                    
                </div>



               <!--  <h2 class="text-2xl text-gray-600 font-bold mb-4">Our Team</h2> -->

               <!--  <div>
                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Our Impact</h2>
                    <p class="text-gray-600">
                        Here at Clean Climate, we are committed to creating a sustainable future through education and awareness. 
                        Since our inception in 2024, we have been dedicated to empowering individuals and communities to make informed decisions for a 
                        climate-resilient world. Join us in making a real difference.
                    </p>

                    <h2 class="text-2xl text-gray-600 font-bold mb-4">Partners</h2>
                </div> -->
            </div>
            <div class="flex flex-col md:flex-row gap-[40px] mt-[100px]">
                <div class="text-gray-600  w-1/2">
                    <h2 class="text-2xl font-bold mb-4 ">Contact Us</h2>
                    <p>Email: info@cleanclimate.com</p>
                    <p>Phone: +233546383716</p>
                </div>
                <ContactForms class="w-auto md:w-1/2" />
            </div>
            
            </div>
        </UContainer>
        
    </div>
</template>


<style>
    .back{
        background-image: url("https://cdn.pixabay.com/photo/2024/04/03/06/09/ai-generated-8672147_1280.jpg");
        background-position: center;
        background-repeat: no-repeat;
        background-size: cover;
    }

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