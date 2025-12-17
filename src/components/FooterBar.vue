<script>
export default {
  name: "FooterBar",
  props: {
    crtext: {
      type: String,
      required: true,
    },
  },
};
</script>
<template>
  <footer class="w-full text-right mr-4.5 mb-1">
    <p class="text-xs text-white">{{ crtext }}</p>
  </footer>
</template>
