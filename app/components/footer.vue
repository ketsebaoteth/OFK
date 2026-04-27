
<script setup lang="ts">
import { onMounted } from 'vue';
onMounted(() => {});
</script>

<template>
  <div class="w-screen h-[70vh] z-500 bg-white pt-0 overflow-hidden">
    <div class="contentholder bg-gray-400 w-full h-full p-32 flex text-black ">

      <div class="w-fit">
        <p class="text-lg font-bold company ">OFK Constructions</p>

        <p class="mt-32 text-gray-700 text-sm">© 2025 DeusMachina, Inc. All rights reserved.</p>
      </div>
      
      <div class="flex flex-col ml-64 text-sm font-light gap-3">
        <p>Contact Us</p>
        <p>About Us</p>
        <p>Work</p>
        <p>FAQ</p>
        <h1 class="mt-20 text-[350px] -ml-10 w-fit">OFK</h1>
      </div>
      <div class="flex flex-col text-sm font-light gap-3">
        <p>Instagram</p>
        <p>X</p>
        <p>Linkedin</p>
        <p>TikTok</p>
      </div>
    </div>
  </div>
</template>

<style lang="css" scoped>
.contentholder {
  background: url('/footerbag.png') no-repeat center center;
  background-position-y: calc(bottom - 50px);
  background-size: cover;
}

@font-face {
  font-family: 'RemixaTest';
  src: url('/RemixaTest-Regular.otf') format('opentype');
}

.company {
  font-family: 'RemixaTest', sans-serif;
}

</style>
