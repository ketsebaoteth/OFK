<script setup lang="ts">
import { onMounted } from "vue";
onMounted(() => {});
</script>

<template>
  <div
    class="relative z-300 flex h-screen w-screen flex-col gap-16 overflow-hidden bg-black p-20"
  >
    <div class="flex flex-col gap-5">
      <h1 class="w-150 text-[80px] leading-20 font-bold">
        What our clients say about us
      </h1>
      <div class="sep-line z-500 h-px w-20 bg-white"></div>
    </div>

    <div class="z-500 flex gap-10">
      <TestimonialCard
        imageurl="/pfp1.jpg"
        name="Andre Tan"
        testimonial="Working with this team was seamless from start to finish. They understood our vision and delivered beyond expectations."
      />
      <TestimonialCard
        imageurl="/pfp2.jpg"
        name="Vince Fleming"
        testimonial="Professional, responsive, and incredibly detail-oriented. The final result made a huge impact on our business."
      />
      <TestimonialCard
        name="Maya Collins"
        imageurl="/pfp1.jpg"
        testimonial="Their creativity and execution were top-notch. We’ve received amazing feedback from our clients ever since launch."
      />
    </div>
    <Testimonialareasvg />
  </div>
</template>

<style lang="css" scoped></style>
