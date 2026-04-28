<script setup lang="ts">
import { onMounted } from "vue";
import gsap from "gsap";

// on mounted animations
onMounted(() => {
  gsap.from(".mainNavBar", {
    delay: 1,
    scaleX: 0,
    transformOrigin: "left",
    duration: 1,
    ease: "expo.out",
  });
  gsap.from(".bookACallBtn", {
    delay: 1,
    scaleX: 0,
    duration: 1,
    ease: "expo.out",
  });
  gsap.from(".navLink", {
    delay: 1.4,
    y: -20,
    autoAlpha: 0, // Better than just opacity
    stagger: 0.1,
    duration: 0.8,
    ease: "expo.out",
    force3D: true, // Ensures hardware acceleration
  });
});
</script>

<template>
  <div class="flex h-14">
    <div
      class="z-[1000] flex h-full w-fit place-items-center gap-8 rounded-full bg-gray-950 p-3"
    >
      <div class="w-10 h-full flex place-items-center justify-center">
        <svg
          id="Layer_1"
          data-name="Layer 1"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 65.58 90.27"
          class="text-white fill-white w-5 h-5"
        >
          <path
            d="m33.8,26.94v-14.68s20.56-1.27,30.4,22.11c1.04,2.46,1.48,5.14,1.36,7.81-1.14,26.13-20.78,38.26-20.78,38.26,0,0-6.76,5.2-8.77,8.53-.09.15-1.17,1.48-1.16,1.3.57-6.22,1.09-18.45,1.09-18.45,0,0,7.5-6.13,15.29-20.07,5.23-9.37-3.26-21.16-8.36-22.95s-9.06-1.85-9.06-1.85Z"
          />
          <path
            d="m32.07,0v19.34s-18.13,14.57-17.74,25.7,9.38,19.36,17.11,19.43v13.98s-19.47.7-28.15-17.55c-6.91-14.54-1.53-29.74,3.51-36.77S32.07,0,32.07,0Z"
          />
        </svg>
      </div>
      <h1 class="font-[Inter] -ml-10 font-extrabold">OFK</h1>
      <div class="navLinksContainer flex flex-row gap-2 text-sm">
        <NuxtLink
          class="navLink niceBounce inline-block rounded-full px-2 py-1 hover:bg-gray-900"
          to="/"
          >Home</NuxtLink
        >
        <NuxtLink
          class="navLink niceBounce inline-block rounded-full px-2 py-1 hover:bg-gray-900"
          to="/posts"
          >Work</NuxtLink
        >
        <NuxtLink
          class="navLink niceBounce inline-block rounded-full px-2 py-1 hover:bg-gray-900"
          to="/about"
          >About</NuxtLink
        >
        <NuxtLink
          class="navLink niceBounce inline-block rounded-full px-2 py-1 hover:bg-gray-900"
          to="/contact"
          >Contact</NuxtLink
        >
      </div>
    </div>
    <div
      class="group bookACallBtn z-50 ml-auto flex h-14 w-fit cursor-pointer place-items-center gap-0 rounded-full bg-gray-950 p-3"
    >
      <h1>Book A Call</h1>
      <div
        class="niceBounce flex w-0 place-items-center justify-center overflow-hidden transition-all duration-300 group-hover:w-8"
      >
        <Icon
          name="tabler:arrow-up-right"
          size="32"
          class="h-8 w-8 overflow-hidden transition-all duration-300 group-hover:w-4"
        />
      </div>
    </div>
  </div>
</template>

<style lang="css">
.niceBounce {
  transition:
    padding-inline 0.4s cubic-bezier(0.34, 1.56, 0.64, 1),
    width 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}
.navLinksContainer a:hover {
  padding-inline: 18px;
}
</style>
