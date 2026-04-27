<script setup lang="ts">
import { onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
import SplitText from 'gsap/src/SplitText'

gsap.registerPlugin(ScrollTrigger, SplitText)

onMounted(() => {
  const target = document.querySelector('.inviewtrig')

  // 1. Double Split for the Masking Effect
  const split = new SplitText(target, { 
    type: "lines", 
    linesClass: "lineParent" 
  })
  
  const innerSplit = new SplitText(split.lines, { 
    type: "lines", 
    linesClass: "lineInner" 
  })

  // 2. Hide the overflow so text "emerges" from nothing
  gsap.set(".lineParent", { overflow: "hidden" })

  // 3. Trigger when the section comes into view
  gsap.from(innerSplit.lines, {
    yPercent: 110,
    duration: 1.2,
    ease: "expo.out",
    stagger: 0.1,
    scrollTrigger: {
      trigger: ".inviewtrig",
      start: "top 40%", 
      toggleActions: "play none none none",
    }
  })


})
</script>

<template>
  <div class="h-screen w-full bg-transparent"></div>

  <section class="secondSection relative w-full flex">
    <div class="w-full h-full py-40 bg-white text-black z-[200] flex flex-col place-items-center">
      
      <h1 class="ml-auto mr-auto text-center animup text-[120px] leading-[110px] w-[800px] inviewtrig">
        Services We Provide
      </h1>

      <div class="flex gap-28 w-full h-fit justify-center mt-10">
        <CardComp 
          title="New Home Construction"
          description="From Blueprint to Doorstep. This emphasizes the full journey and the emotional moment of finally walking into a brand-new home."
          imageurl="/home-con.avif"
        />
        
        <CardComp 
          title="Full-Scale Renovations"
          imageurl="/re.jpg"
          description="Love the Home You’re Already In. This appeals to the &quot;transformation&quot; aspect, reminding clients that they don't need to move to get the space they’ve always wanted."
        />
        
        <CardComp 
          title="Site & Project Management"
          imageurl="/sitemanage.jpg"
          description="Precise Planning. Zero Surprises.&quot; In construction, &quot;surprises&quot; usually mean extra costs."
        />
      </div>

      <div class="mt-20 cursor-pointer notstiff hover:px-6 flex place-items-center px-5 py-2 border-2 w-fit border-gray-950 rounded-full">
        <p class="font-bold">About Us</p>
        <Icon name="tabler:arrow-up-right" size="32" class="w-8 h-8 ml-2 inline-block" />
      </div>
    </div>
  </section>
</template>

<style lang="css" scoped>
.notstiff {
  transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
}

/* This ensures the split lines don't clip descenders like 'y' or 'g' */
:deep(.lineParent) {
  padding-bottom: 0.1em;
  margin-bottom: -0.1em;
}
</style>