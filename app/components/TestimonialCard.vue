
<script setup lang="ts">
import { onMounted } from 'vue';

let props =  defineProps({
  name: String,
  testimonial: String,
  imageurl: String
})
onMounted(() => {});
</script>

<template>
  <div class="w-120 h-fit py-20 bg-[#111111] flex flex-col gap-8 place-items-center rounded-2xl p-5">
    <div class="profile relative w-20 h-20 rounded-full">
      <NuxtImg :src="props.imageurl" class="absolute top-0 left-0 w-30 h-25 rounded-full object-cover z-10 blur-md opacity-20" />
      <NuxtImg :src="props.imageurl" class="w-20 h-20 rounded-full object-cover z-20 relative" />
    </div>
    <h1 class="text-white text-[28px] font-bold">{{ props.name }}</h1>
    <p class="text-gray-600 text-center mx-10"><span class="text-2xl">"</span>{{ props.testimonial }}<span class="text-2xl">"</span></p>
  </div>
</template>

<style lang="css" scoped>
</style>
