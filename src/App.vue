<script>
import AppBar from "./components/AppBar.vue";
import Button from "./components/Button.vue";
import Dialog from "./components/Dialog.vue";
import FooterBar from "./components/FooterBar.vue";
import SnowParticles from "./components/SnowParticles.vue";

import Verse from "./data/verse.json";

export default {
  components: {
    AppBar,
    Button,
    Dialog,
    FooterBar,
    SnowParticles,
  },
  data() {
    return {
      isDialogOpen: false,
      selectedVerse: null,
    };
  },
  methods: {
    openDialog() {
      const randomIdx = Math.floor(Math.random() * Verse.length);
      this.selectedVerse = Verse[randomIdx];
      this.isDialogOpen = true;
    },
  },
};
</script>
<template class="flex flex-col gap-2">
  <SnowParticles />
  <main class="flex flex-col items-center justify-between min-h-screen">
    <AppBar title="MTHC" subtitle="More than Hot Chocolate" />

    <div class="flex flex-col items-center justify-between px-5 my-5">
      <div class="text-white flex flex-col">
        <h1 class="font-display text-5xl md:text-7xl">Merry Christmas</h1>
        <p class="text-right text-base md:text-lg">and Happy New Year!</p>
      </div>

      <img src="/src/assets/christmasTree.webp" class="w-64" />
      <div class="flex flex-col gap-3 items-center justify-center">
        <p class="text-white text-center text-base">
          God's love warms the soul more than hot chocolate ever could.
        </p>
        <Button label="Take a Sip!" variant="yellow" @click="openDialog" />
        <Dialog
          v-if="isDialogOpen && selectedVerse"
          :bibver="selectedVerse"
          @close="isDialogOpen = false"
        />
      </div>
    </div>
    <FooterBar crtext=" Copyright © 2025 Letstray. All Rights Reserved." />
  </main>
</template>
