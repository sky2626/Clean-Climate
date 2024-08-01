<template>
    <div classs="">
        <UContainer class="pt-[100px]">
            <div class="flex gap-[8px] flex-col">
                <div class="overflow-hidden md:h-96">
                    <img class="rounded-xl" src="/public/bg.jpg" alt="">
                </div>
                <UAccordion
                default-open
                multiple
                :items="[{ label: 'What is Climate?', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit' }, 
                ]"
                />
            </div>
            <div class="flex gap-[8px] flex-col">
                <div class="overflow-hidden md:h-96">
                    <img class="rounded-xl" src="/public/bg.jpg" alt="">
                </div>
                <UAccordion
                default-open
                multiple
                :items="[{ label: 'What is Climate?', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit' }, 
                ]"
                />
            </div>
            <div class="flex gap-[8px] flex-col">
                <div class="overflow-hidden md:h-96">
                    <img class="rounded-xl" src="/public/bg.jpg" alt="">
                </div>
                <UAccordion
                default-open
                multiple
                :items="[{ label: 'What is Climate?', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit' }, 
                ]"
                />
            </div>
            <div class="flex gap-[8px] flex-col">
                <div class="overflow-hidden md:h-96">
                    <img class="rounded-xl" src="/public/bg.jpg" alt="">
                </div>
                <UAccordion
                default-open
                multiple
                :items="[{ label: 'What is Climate?', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit' }, 
                ]"
                />
            </div>
            <div class="flex gap-[8px] flex-col">
                <div class="overflow-hidden md:h-96">
                    <img class="rounded-xl" src="/public/bg.jpg" alt="">
                </div>
                <UAccordion
                default-open
                multiple
                :items="[{ label: 'What is Climate?', content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit' }, 
                ]"
                />
            </div>
            <div class="flex justify-center items-center">
                <UPagination v-model="page" :total="items.length" :ui="{ rounded: 'first-of-type:rounded-s-md last-of-type:rounded-e-md' }">
                <template #prev="{ onClick }">
                    <UTooltip text="Previous page">
                        <UButton icon="i-heroicons-arrow-small-left-20-solid" color="primary" :ui="{ rounded: 'rounded-full' }" class="rtl:[&_span:first-child]:rotate-180 me-2" @click="onClick" />
                    </UTooltip>
                </template>

                    <template #next="{ onClick }">
                        <UTooltip text="Next page">
                            <UButton icon="i-heroicons-arrow-small-right-20-solid" color="primary" :ui="{ rounded: 'rounded-full' }" class="rtl:[&_span:last-child]:rotate-180 ms-2" @click="onClick" />
                        </UTooltip>
                    </template>
                </UPagination>
            </div>
        </UContainer>
    </div>
</template>

<script setup lang="ts">
const page = ref(1)
const items = ref(Array(55))
</script>