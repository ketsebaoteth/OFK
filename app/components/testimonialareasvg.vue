<script setup lang="ts">
import { onMounted } from "vue";
onMounted(() => {});
</script>

<template>
  <div class="absolute bottom-10 left-10 z-[400] w-64 scale-200">
    <svg
      id="Layer_1"
      data-name="Layer 1"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="-200 -200 1200 900"
      class="h-auto w-full overflow-visible scale-200"
    >
      <defs>
        <filter id="blur-grain" x="-50%" y="-50%" width="200%" height="200%">
          <feGaussianBlur in="SourceGraphic" stdDeviation="50" result="blurred" />
          <feTurbulence type="fractalNoise" baseFrequency="0.85" numOctaves="4" result="noise" />
          <feColorMatrix in="noise" type="saturate" values="0" result="destaturatedNoise" />
          <feComposite in="destaturatedNoise" in2="blurred" operator="in" result="clippedNoise" />
          <feBlend in="blurred" in2="clippedNoise" mode="multiply" opacity="0.2" />
        </filter>
      </defs>

      <path
        class="cls-1"
        filter="url(#blur-grain)"
        d="m20,139.7C74,87.7,86,41.7,175,14.7s155-25,177,77-167,28-113,143,169,143,242,32,192-59,240,23,136,139,32,172S0,466.7,0,466.7L20,139.7Z"
      />
    </svg>
  </div>
</template>

<style lang="css" scoped>
.cls-1 {
  fill: #f15a24;
}
</style>
