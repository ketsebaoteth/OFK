
<script setup lang="ts">
import { onMounted } from 'vue';
onMounted(() => {});
</script>

<template>
  <div class="w-screen h-[170vh] py-20 p-10 bg-white text-black z-400 flex flex-col gap-20 place-items-center justify-center">
    <h1 class="text-[120px] leading-22 w-180 text-center ">Meet Our Team</h1>
    <NuxtImg
      src="/ourteam.jpg"
      class="w-full h-auto object-cover"
    />
  </div>
</template>

<style lang="css" scoped>
</style>
