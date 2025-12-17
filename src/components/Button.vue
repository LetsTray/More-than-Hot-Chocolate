<script>
export default {
  name: "Button",
  props: {
    label: {
      type: String,
      required: true,
    },
    variant: {
      type: String,
      default: "green",
      validator: (value) => ["green", "yellow"].includes(value),
    },
  },
  computed: {
    computedVariantClass() {
      const variantClass = {
        green:
          " border border-[#BBD882] text-[#BBD882] hover:bg-[#6E9036] hover:border-[#6E9036] hover:text-white transition-colors duration-300 ",
        yellow:
          " border border-[#FBF19F] text-[#FBF19F] text-[#D76131] hover:bg-[#C7542E] hover:border-[#C7542E] hover:text-[#FBF19F] transition-colors duration-300",
      };
      return variantClass[this.variant];
    },
  },
};
</script>
<template>
  <button
    :class="[
      'w-fit',
      'px-3.5',
      'py-1.5',
      'font-medium',
      'item-center',
      'rounded-4xl',
      'text-base',
      'cursor-pointer',
      computedVariantClass,
    ]"
  >
    {{ label }}
  </button>
</template>
