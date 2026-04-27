
<script setup lang="ts">
import { onMounted } from 'vue';
import gsap from 'gsap';

// on mounted animations
onMounted(() => {
  gsap.from(".mainNavBar",{
    delay: 1,
    scaleX: 0,
    transformOrigin: "left",
    duration: 1,
    ease: "expo.out"
  })
  gsap.from(".bookACallBtn",{
    delay: 1,
    scaleX: 0,
    duration: 1,
    ease: "expo.out",
  })
  gsap.from (".navLink", {
    delay: 1.4,
    y: -20,
    autoAlpha: 0, // Better than just opacity
    stagger: 0.1,
    duration: 0.8,
    ease: "expo.out",
    force3D: true // Ensures hardware acceleration
    })
});
</script>

<template>
  <div class="h-14 flex">
    <div class=" p-3 bg-gray-950 rounded-full h-full w-fit flex place-items-center gap-8 z-[1000]">
          <h1 class="font-[Inter] font-extrabold">OFK</h1>
          <div class="flex flex-row gap-2 text-sm navLinksContainer ">
            <NuxtLink class="navLink inline-block px-2 py-1 rounded-full hover:bg-gray-900 niceBounce" to="/">Home</NuxtLink>
            <NuxtLink class="navLink inline-block px-2 py-1 rounded-full hover:bg-gray-900 niceBounce" to="/posts">Work</NuxtLink>
            <NuxtLink class="navLink inline-block px-2 py-1 rounded-full hover:bg-gray-900 niceBounce" to="/about">About</NuxtLink>
            <NuxtLink class="navLink inline-block px-2 py-1 rounded-full hover:bg-gray-900 niceBounce" to="/contact">Contact</NuxtLink>
          </div>
      </div>
      <div class="group bookACallBtn ml-auto flex place-items-center gap-0 bg-gray-950 rounded-full p-3  h-14 w-fit cursor-pointer z-50">
            <h1>Book A Call</h1>
            <div class="overflow-hidden w-0 flex place-items-center justify-center group-hover:w-8 transition-all duration-300 niceBounce">
            <Icon 
              name="tabler:arrow-up-right" 
              size="32"
              class="w-8 h-8 overflow-hidden transition-all duration-300 group-hover:w-4" 
            />
            </div>

          </div>
      </div>
  
</template>

<style lang="css">
.niceBounce{
 transition: padding-inline 0.4s cubic-bezier(0.34, 1.56, 0.64, 1),
             width 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}
.navLinksContainer a:hover {
  padding-inline: 18px;
}
</style>
