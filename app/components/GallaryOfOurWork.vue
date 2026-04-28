
<script setup lang="ts">
import { onMounted } from 'vue';
onMounted(() => {});
</script>

<template>
  <div class="w-screen h-[110vh] bg-white z-400 flex flex-col gap-10 place-items-center justify-center">
    <h1 class="text-black text-[120px] w-130 leading-26 text-center">Gallery of Our Work</h1>
    <div class="flex w-full h-full">
      <NuxtImg
        src="/gallery1.jpg"
        class="w-1/3 h-full object-cover"
      />
      <NuxtImg
        src="/gallery2.jpg"
        class="w-1/3 h-full object-cover"
      />
      <NuxtImg
        src="/gallery3.jpg"
        class="w-1/3 h-full object-cover"
      />
    </div>
  </div>
</template>

<style lang="css" scoped>
</style>
