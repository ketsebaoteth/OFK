<script setup lang="ts">
import { onMounted, useTemplateRef } from 'vue'; // useTemplateRef is great for Vue 3.4+
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

let props = defineProps({
  title: String,
  description: String,
  imageurl: String
})

// Use a ref to target ONLY the element in this specific component instance
const separatorRef = useTemplateRef('separator');

onMounted(() => {
  if (separatorRef.value) {
    gsap.from(separatorRef.value, {
      scaleX: 0,
      transformOrigin: "left",
      duration: 1.5,
      ease: "expo.out",
      scrollTrigger: {
        trigger: separatorRef.value, // Trigger on this specific separator
        start: "top 60%",           // Animation starts when it's near the bottom
        toggleActions: "play none none none",
      }
    });
  }
});
</script>

<template>
  <div class="w-[380px] h-[600px] mt-20 p-3 rounded-2xl flex flex-col">
    <div class="w-full h-[250px] bg-white rounded-xl overflow-hidden">
      <NuxtImg :src="props.imageurl" class="w-full h-full rounded-3xl object-cover" />
    </div>
    
    <h1 class="text-[43px] font-bold leading-[50px] mt-8">{{ props.title }}</h1>
    
    <div ref="separator" class="w-[50px] h-[1px] bg-black my-5 separator" />
    
    <p class="mt-2 text-gray-700">
      {{ props.description }}
    </p>
  </div>
</template>