<!-- src/components/HeroSection.vue -->
<script setup>
import LeftCoin from '/src/assets/imgs/left.png'
import RightCoin from '/src/assets/imgs/right.png'
</script>

<template>
  <div class="relative isolate px-6 pt-14 lg:px-8">
    <img class="absolute left-30 top-50 h-30 w-auto" :src="LeftCoin" alt="Mermeme Coin" />
    <img class="absolute right-40 top-80 h-30 w-auto" :src="RightCoin" alt="Mermeme Coin" />

    <div class="absolute inset-x-0 -top-40 -z-10 transform-gpu overflow-hidden blur-3xl sm:-top-80" aria-hidden="true">
      <div
        class="relative left-[calc(50%-11rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff625a] to-[#5468ff] opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>
    <div class="mx-auto max-w-2xl py-32 sm:py-48 lg:py-56">
      <div class="hidden sm:mb-8 sm:flex sm:justify-center">
        <div class="relative rounded-full px-3 py-1 text-sm text-white ring-1 ring-green-900 hover:ring-green-800">
          Announcing our next round of funding.
          <a href="#" class="font-semibold text-indigo-400 hover:text-indigo-300">
            <span class="absolute inset-0" aria-hidden="true" />
            Read more <span aria-hidden="true">&rarr;</span>
          </a>
        </div>
      </div>
      <div class="text-center">
        <h1 class="text-5xl font-semibold tracking-tight text-balance text-white sm:text-7xl">
          Splash, Laugh, Moon, Repeat...
        </h1>
        <p class="mt-8 text-lg font-medium text-pretty text-gray-100 sm:text-xl">
          A meme coin that washed up on the crypto beach, bringing bubbles and questionable decisions
        </p>
        <div class="mt-10 flex items-center justify-center gap-x-6">
          <a href="#" class="inline-flex items-center justify-center h-12 px-6 rounded-md font-mono text-white text-lg bg-gradient-to-tr from-[#5affa4] to-[#34af57] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#3fe07b] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#3fe07b] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#3fe07b]">
            Get Started
          </a>
          <a href="#" class="text-sm font-semibold text-white hover:text-indigo-400 transition-colors">
            Learn more <span aria-hidden="true">→</span>
          </a>
        </div>
      </div>
    </div>
    <div
      class="absolute inset-x-0 top-[calc(100%-13rem)] -z-10 transform-gpu overflow-hidden blur-3xl sm:top-[calc(100%-30rem)]"
      aria-hidden="true">
      <div
        class="relative left-[calc(50%+3rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 bg-gradient-to-tr from-[#5adaff] to-[#5468ff] opacity-30 sm:left-[calc(50%+36rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>
  </div>
</template>
