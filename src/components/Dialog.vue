<script>
export default {
  name: "Dialog",
  props: {
    bibver: {
      type: Object,
      required: true,
    },
  },
  emits: ["close"],
};
</script>
<template>
  <Teleport to="body">
    <div
      class="fixed inset-0 bg-black/50 z-50 flex items-center justify-center"
      @click.self="$emit('close')"
    >
      <div
        class="bg-white flex flex-col gap-4 max-h-11/12 w-full mx-7 md:w-lg lg:w-xl rounded-4xl p-4 bg-linear-to-r from-[#E2794E] to-[#F3C058]"
      >
        <div class="rounded-3xl px-7 py-6 bg-white flex flex-col gap-3 text-justify">
          <p class="">
            {{ bibver.content }}
          </p>
          <p class="text-sm font-semibold text-right">
            <i>{{ bibver.verse }}</i>
          </p>
        </div>
      </div>
    </div>
  </Teleport>
</template>
