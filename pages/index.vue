<template>
    <div class="bg-white screen ">
        <div class=" bg-white screen">
            <HeroSection />
        </div>
        
        <div class="px-[18px] mt-8 gap-[18px] flex flex-col md:flex-row justify-center" >
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
        <div class="flex flex-col md:flex-row justify-center items-center gap-[18px] mt-24">
            <div class="flex bg-[#e9fbc9] flex-row flex-col bg- rounded-[40px] px-36 md:px-24 py-[48px] justify-center">
                <h2 class="text-xl font-bold text-[#486415]">We</h2>
            </div>
            <div class="flex bg-[#3c487d] flex-row flex-col rounded-[40px] px-36 md:px-24 py-[48px] justify-center">
                <h2 class="text-xl font-bold text-[#c9d2fb]">Protect</h2>
            </div>
            <div class="flex bg-[#fbdfc9] flex-row flex-col rounded-[40px] px-36 md:px-24 py-[48px] justify-center">
                <img src="/arrow.svg" alt="arrow image">
            </div>
            <div class="flex bg-[#c9fbf9] flex-row flex-col rounded-[40px] px-36 md:px-24 py-[48px] justify-center">
                <h2 class="text-xl font-bold text-[#185755]">Nature</h2>
            </div>
        </div>
        <div class="flex flex-col md:flex-row px-[18px] md:px-[450px] justify-center items-center md:justify-between mt-[18px]">
            <h1 class="text-gray-600 text-4xl font-extrabold text-center md:text-start">Our initiatives for the 2024</h1>
            <p class="text-gray-400 text-center md:text-end w-[300px]">Find out the projects that we are undertaking this year.</p>
        </div>
        <div class="flex justify-center mt-[24px]"> 
            <UContainer>
                <Table />
            </UContainer>           
            
        </div>
    </div>
</template>


<script>

</script>