<script>
import { onMounted } from "vue";
export default {
  name: "SnowParticles",
  mounted() {
    particlesJS("particles-js", {
      particles: {
        number: {
          value: 120,
          density: { enable: true, value_area: 800 },
        },
        color: { value: "#ffffff" },
        shape: { type: "circle" },
        opacity: { value: 0.8 },
        size: {
          value: 3,
          random: true,
        },
        line_linked: {
          enable: false,
        },
        move: { enable: true, speed: 1, direction: "bottom", out_mode: "out" },
      },
      retina_detect: true,
    });
  },
};
</script>
<template>
  <div id="particles-js" class="fixed inset-0 z-50 pointer-events-none"></div>
</template>
