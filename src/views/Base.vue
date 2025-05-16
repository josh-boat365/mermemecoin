<!-- src/views/Base.vue -->
<script setup>
import NavBar from '@/components/NavBar.vue'
import Hero from '@/components/Hero.vue'
</script>

<template>
  <div class="relative">
    <!-- 1. Base green gradient -->
    <div class="absolute inset-0 bg-gradient-to-b from-[#0f3720] via-[#084f1b] to-[#023507]"></div>

    <!-- 2. Neon blobs (updated versions) -->
    <!-- Top blob -->
    <div class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80" aria-hidden="true">
      <div
        class="relative left-[calc(50%-11rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ffea00] via-[#5eff00] to-[#ff8400] opacity-40 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>

    <!-- Bottom blob -->
    <div
      class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
      aria-hidden="true">
      <div
        class="relative left-[calc(50%+3rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-[#ffea00] via-[#5eff00] to-[#ff8400] opacity-40 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>

    <!-- 3. Dot pattern overlay -->
    <div
      class="absolute inset-0 [background-image:radial-gradient(#18d257_0.65px,transparent_0.65px)] [background-size:15px_15px] opacity-40">
    </div>

    <!-- 4. Content container -->
    <div class="relative z-10">
      <NavBar />
      <Hero />
    </div>
  </div>
</template>
