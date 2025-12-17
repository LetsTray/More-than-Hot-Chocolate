<script>
export default {
  name: "AppBar",
  props: {
    title: {
      type: String,
      required: true,
    },
    subtitle: {
      type: String,
      required: true,
    },
  },
};
</script>
<template>
  <header
    class="w-full bg-black flex justify-between items-center px-4.5 py-2.5 top-0 sticky"
  >
    <div class="flex-col">
      <h1 class="text-white text-4xl font-bold">{{ title }}</h1>
      <p class="text-white text-xs">{{ subtitle }}</p>
    </div>
  </header>
</template>
