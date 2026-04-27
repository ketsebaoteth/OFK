<script setup lang="ts">
import { ref } from 'vue';
import gsap from 'gsap';

const faq_questions = [
  {
    question: "What services do you offer?",
    answer: "We offer a wide range of services including web development, mobile app development, UI/UX design, and digital marketing."
  },
  {
    question: "How long does a typical project take?",
    answer: "The timeline varies based on the project scope, but most projects are completed within 4-12 weeks."
  },
  {
    question: "What is your pricing model?",
    answer: "We offer both fixed-price and hourly pricing models depending on the client's needs and project requirements."
  },
]

const activeIndex = ref<number | null>(null);

const toggleFAQ = (index: number) => {
  // Select all elements and convert to Array to satisfy TypeScript
  const content = Array.from(document.querySelectorAll('.faq-content'));
  const icons = Array.from(document.querySelectorAll('.faq-icon'));

  const currentContent = content[index];
  const currentIcon = icons[index];
    if(currentIcon){
    gsap.set(currentIcon, { transformOrigin: "center" });
  }

  // 1. Handle Closing if clicking the same one
  if (activeIndex.value === index) {
    if (currentContent) gsap.to(currentContent, { height: 0, duration: 0.5, ease: "expo.inOut" });
    if (currentIcon) gsap.to(currentIcon, { rotate: 0, duration: 0.5 });
    activeIndex.value = null;
    return;
  }

  // 2. Close the previously opened item
  if (activeIndex.value !== null) {
    const prevContent = content[activeIndex.value];
    const prevIcon = icons[activeIndex.value];
    if (prevContent) gsap.to(prevContent, { height: 0, duration: 0.5, ease: "expo.inOut" });
    if (prevIcon) gsap.to(prevIcon, { rotate: 0, duration: 0.5 });
  }

  // 3. Open the new item
  if (currentContent) {
    gsap.to(currentContent, { height: "auto", duration: 0.6, ease: "expo.out" });
  }
  if (currentIcon) {
    gsap.to(currentIcon, { rotate: 45, duration: 0.5, ease: "back.out(2)" });
  }
  
  activeIndex.value = index;
};
</script>

<template>
  <section class="w-full min-h-screen bg-white px-28 flex flex-col items-center py-28 relative z-[400]">
    <h1 class="text-black text-center text-[clamp(60px,10vw,120px)] font-bold leading-none mb-20">
      FAQ <span class="text-lg -ml-5">?</span>
    </h1>

    <div class="flex flex-col w-full max-w-[1000px]">
      <div 
        v-for="(item, index) in faq_questions" 
        :key="index" 
        class="w-full border-b border-gray-300 py-8 cursor-pointer group"
        @click="toggleFAQ(index)"
      >
        <div class="flex justify-between items-center gap-10">
          <h2 class="text-[clamp(20px,4vw,32px)] font-bold text-gray-800 transition-colors group-hover:text-black">
            {{ item.question }}
          </h2>
          <div class="faq-icon text-4xl text-gray-400 select-none">+</div>
        </div>

        <div class="faq-content h-0 overflow-hidden">
          <p class="text-gray-600 text-[clamp(16px,2vw,20px)] pt-6 max-w-[800px] leading-relaxed">
            {{ item.answer }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>