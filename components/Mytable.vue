<template>
  <UTable
    sort-asc-icon="i-heroicons-arrow-up-20-solid"
    sort-desc-icon="i-heroicons-arrow-down-20-solid"
    :sort-button="{ icon: 'i-heroicons-sparkles-20-solid', color: 'primary', variant: 'outline', size: '2xs', square: false, ui: { rounded: 'rounded-full' } }"
    class="w-full"
    :columns="[{ key: 'name', label: 'Activity', sortable: true }, { key: 'title', label: 'Date', sortable: true }, { key: 'email', label: 'Status', sortable: true }, ]"
    :rows="[{ name: 'Lunching of site', title: '02/08/2024', email: 'Completed',  }, 
    { name: 'Populating site', title: '03/08/2024', email: 'Completed', }, 
    { name: 'Going Viral', title: '04/08/2024', email: 'Completed',  }, 
    ]"
  />
</template>
