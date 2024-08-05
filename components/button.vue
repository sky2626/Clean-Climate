<template>
    <button :type="type" :class="buttonClasses" @click="$emit('click')">
      <slot />
    </button>
</template>
  
<script>
  export default {
    name: 'Button',
    props: {
      type: {
        type: String,
        default: 'button',
      },
      variant: {
        type: String,
        default: 'primary',
      },
      size: {
        type: String,
        default: 'md',
      },
      disabled: {
        type: Boolean,
        default: false,
      },
    },
    computed: {
      buttonClasses() {
        return [
          'py-2',
          'px-4',
          'rounded-full',
          'font-medium',
          this.variantClass,
          this.sizeClass,
          this.disabled ? 'opacity-50 cursor-not-allowed' : '',
        ];
      },
      variantClass() {
        switch (this.variant) {
          case 'primary':
            return 'bg-green-600 text-white hover:bg-green-700';
          case 'secondary':
            return 'bg-gray-200 text-gray-700 hover:bg-gray-300';
          // Add more variants as needed
          default:
            return '';
        }
      },
      sizeClass() {
        switch (this.size) {
          case 'sm':
            return 'text-sm';
          case 'md':
            return 'text-base';
          case 'lg':
            return 'text-lg';
          default:
            return '';
        }
      },
    },
  };
</script>
  