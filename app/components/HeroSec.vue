
<script setup lang="ts">
import { onMounted } from 'vue';
import gsap from 'gsap';
import SplitText from 'gsap/src/SplitText';
import ScrollTrigger from 'gsap/src/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  // 1. Split into lines first
  const split = new SplitText(".headingText", { 
    type: "lines",
    linesClass: "lineParent" // This is our "mask"
  });

  // 2. Split again to create an inner container for each line
  const innerSplit = new SplitText(split.lines, {
    type: "lines",
    linesClass: "lineInner" // This is what we actually animate
  });

  // 3. Set up the masking
  // The parent stays still and hides anything outside its bounds
  gsap.set(".lineParent", { overflow: "hidden" });

  // 4. Animate the INNER lines
  gsap.from(innerSplit.lines, {
    y: "110%", // Start fully below the parent line's crop
    duration: 1.2,
    ease: "expo.out",
    stagger: 0.1,
    delay: 1,
  });

  const splitdesc = new SplitText(".descriptionText", { 
    type: "lines",
    linesClass: "lineParentDesc" // This is our "mask"
  });

  const innerSplitDesc = new SplitText(splitdesc.lines, {
    type: "lines",
    linesClass: "lineInnerDesc" // This is what we actually animate
  });

  gsap.set(".lineParentDesc", { overflow: "hidden" });

  gsap.from(innerSplitDesc.lines, {
    y: "110%", // Start fully below the parent line's crop
    duration: 1.2,
    ease: "expo.out",
    stagger: 0.1,
    delay: 1.5,
  });
  gsap.from(".lightBlackCover",{
    delay: 1.8,
    opacity: 0,
    duration: 1.2,
    ease: "expo.in",
  })


})

</script>

<template>
  <div class="h-full w-full flex flex-col fixed top-0 left-0 p-5">
    <MainNav />
    <NuxtImg src="/sky.jpg" alt="Hero Image" class="w-screen h-screen absolute top-0 left-0 object-cover brightness-100" />
    <div class="flex grow place-items-end">
      <div class="h-full grow z-10 flex place-items-end">
        <h1 class="text-[8.2rem] w-[66rem] mt-auto mb-10 leading-[120px] headingText font-bold">Seamless Process Faster Results</h1>
      </div>
      <div class="flex flex-col gap-5 mb-32 z-10 place-items-end">
        <p class="text-right w-[400px] descriptionText leading-[20px]">A smart way to build, renovate, and deliver lasting structures with precision and speed.</p>
        <p>[ Scroll Down ]</p>
      </div>
      <div class="absolute lightBlackCover top-0 left-0 w-screen h-screen opacity-20 z-5" ></div>
    </div>
  </div>
  
</template>

<style lang="css" scoped>
@font-face {
  font-family: 'RemixaTest';
  src: url('/RemixaTest-Regular.otf') format('opentype');
}

.headingText {
  font-family: 'RemixaTest', sans-serif;
}

.lightBlackCover{
  background: #000000;
background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 1) 100%);
}
</style>
