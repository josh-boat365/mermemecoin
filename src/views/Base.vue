<!-- src/views/Base.vue -->
<script setup>
import NavBar from '@/components/NavBar.vue'
import Hero from '@/components/Hero.vue'
import CryptoLogos from '@/components/About.vue';
import TransactionInfo from '@/components/TransactionInfo.vue';
import CTA from '@/components/CTA.vue';
import Footer from '@/components/Footer.vue';
</script>

<template>
  <div class="relative">
    <!-- 1. Base green gradient -->
    <div class="absolute inset-0 bg-gradient-to-b from-[#155b64] via-[#093762] to-[#022335]"></div>

    <!-- 2. Neon blobs (updated versions) -->
    <!-- Top blob -->
    <div class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80" aria-hidden="true">
      <div
        class="relative left-[calc(50%-11rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ffae00] via-[#008cff] to-[#ff8400] opacity-40 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>



    <!-- Dot pattern overlay -->
    <div class="absolute inset-0 bg-dotted opacity-40" style="--dot-color: yellow; --dot-spacing: 10px"></div>


    <!-- 3. Content container -->
    <div class="relative z-10">
      <NavBar />
      <Hero />
      <CryptoLogos />
      <CTA />
      <TransactionInfo />
      <Footer />
    </div>
  </div>
</template>
