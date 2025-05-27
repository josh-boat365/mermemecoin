<!-- src/components/HeroSection.vue -->
<script setup>
import LeftCoin from '@/assets/imgs/Left.webp'
import RightCoin from '@/assets/imgs/Right.webp'
import { ref, onMounted, onUnmounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

// Register GSAP ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

// GSAP animation for the hero section
const heroSection = ref(null)

// Coin animation control
let coinAnimationFrame
const animateCoins = () => {
  const leftCoin = document.querySelector('.left-coin')
  const rightCoin = document.querySelector('.right-coin')

  if (leftCoin && rightCoin) {
    const time = Date.now() * 0.100 // Get time in seconds
    const moveDistance = 15 // How much they move up/down

    // Left coin animation (rotate and float)
    leftCoin.style.transform = `
      translateY(${Math.sin(time * 2.0) * moveDistance}px)
      rotate(${time * 80}deg)
    `

    // Right coin animation (rotate and float with offset)
    rightCoin.style.transform = `
      translateY(${Math.cos(time * 2) * moveDistance}px)
      rotate(${time * 75}deg)
    `
  }

  coinAnimationFrame = requestAnimationFrame(animateCoins)
}

// Mouse tracking blob effect
const mouseX = ref(0)
const mouseY = ref(0)
const blobX = ref(0)
const blobY = ref(0)
const isHovering = ref(false)
let blobAnimationFrame

const handleMouseMove = (e) => {
  mouseX.value = e.clientX
  mouseY.value = e.clientY
  isHovering.value = true
}

const handleMouseLeave = () => {
  isHovering.value = false
}

const animateBlob = () => {
  // Smooth follow effect with easing
  blobX.value += (mouseX.value - blobX.value) * 0.05
  blobY.value += (mouseY.value - blobY.value) * 0.05

  blobAnimationFrame = requestAnimationFrame(animateBlob)
}

onMounted(() => {
  animateCoins()
  animateBlob()
  window.addEventListener('mousemove', handleMouseMove)

  // GSAP animation for the hero section
  gsap.from(heroSection.value,{
    scrollTrigger: {
      trigger: heroSection.value,
      start: 'top 80%',
      toggleActions: 'play none none none',
    },
    opacity: 0,
    y: 50,
    duration: 1,
    ease: 'power2.out',
    immediateRender: false,
  })

  gsap.from(heroSection.value.querySelectorAll('h1, p, a'), {
    scrollTrigger: {
      trigger: heroSection.value,
      start: 'top 80%',
    },
    opacity: 0,
    y: 50,
    duration: 1,
    stagger: 0.5,
    ease: 'power2.out',
    immediateRender: false,
  })


  ScrollTrigger.refresh()
})

onUnmounted(() => {
  cancelAnimationFrame(coinAnimationFrame)
  cancelAnimationFrame(blobAnimationFrame)
  window.removeEventListener('mousemove', handleMouseMove)
})
</script>

<template>
  <div
  ref="heroSection"
   class="relative isolate px-6 pt-16 pb-16 lg:px-8 overflow-hidden" @mousemove="handleMouseMove"
    @mouseleave="handleMouseLeave">

    <!-- Mouse-following gradient blob -->
    <div
      class="absolute -z-20 w-[600px] h-[600px] rounded-full opacity-20 blur-3xl transition-opacity duration-500 pointer-events-none"
      :class="{ 'opacity-30': isHovering, 'opacity-10': !isHovering }" :style="{
  background: 'radial-gradient(circle, rgba(195,146,0,50) 0%, rgba(162,0,195,50) 50%, transparent 70%)',
        transform: `translate(calc(${blobX}px - 50%), calc(${blobY}px - 50%))`,
        left: 0,
        top: 0,
        transition: 'transform 0.1s linear'
      }"></div>

    <!-- Animated coins -->
    <img class="left-coin absolute hidden sm:block h-[120px] w-auto -z-10 transition-transform duration-300"
      :src="LeftCoin" alt="Mermeme Coin" :style="{
        left: '10%',
        top: '20%',
        maxWidth: 'min(150px, 20vw)'
      }" />

    <img class="right-coin absolute hidden sm:block h-[120px] w-auto z-10 transition-transform duration-300"
      :src="RightCoin" alt="Mermeme Coin" :style="{
        right: '10%',
        top: '33%',
        maxWidth: 'min(150px, 20vw)'
      }" />

    <!-- Existing background elements -->
    <div class="absolute inset-x-0 -top-40 -z-30 transform-gpu overflow-hidden blur-3xl sm:-top-80" aria-hidden="true">
      <div
        class="relative left-[calc(50%-11rem)] aspect-1155/678 w-[36.125rem] -translate-x-1/2 rotate-[30deg] bg-gradient-to-tr from-[#ff625a] to-[#5468ff] opacity-30 sm:left-[calc(50%-30rem)] sm:w-[72.1875rem]"
        style="clip-path: polygon(74.1% 44.1%, 100% 61.6%, 97.5% 26.9%, 85.5% 0.1%, 80.7% 2%, 72.5% 32.5%, 60.2% 62.4%, 52.4% 68.1%, 47.5% 58.3%, 45.2% 34.5%, 27.5% 76.7%, 0.1% 64.9%, 17.9% 100%, 27.6% 76.8%, 76.1% 97.7%, 74.1% 44.1%)" />
    </div>
    <div class="mx-auto max-w-2xl py-12 sm:py-48 lg:py-25 relative z-10">
      <div class="mb-4 flex justify-center sm:mb-8">
        <div class="relative rounded-full px-3 py-1 text-xs bg-[#910b983a] text-gray-100 ring-1 ring-purple-950 hover:ring-purple-500">
          🚀 New Meme Coin on Solana
          <span class="font-semibold text-purple-400">#MermemeCoin</span>
        </div>
      </div>
      <div class="text-center">
        <h1 class="text-5xl font-black text-balance text-white sm:text-7xl">
          <!-- Dive into mermeme coin -->
          Dive deep into the meme sea, <br> Meet $Mermeme Coin
        </h1>
        <p class="mt-8 text-lg font-medium text-pretty text-gray-100 sm:text-xl">
          <!-- A meme coin that washed up on the crypto beach, bringing bubbles and questionable decisions -->
          The ocean's funniest coin is here to make waves. <br> Powered by memes, community and chaos.
        </p>
        <div class="mt-10 flex flex-wrap gap-y-6 items-center justify-center gap-x-6">
          <a href="#"
            class="inline-flex items-center justify-center h-12 px-6 rounded-md text-white text-lg bg-gradient-to-tr from-[#ff655a] to-[#af3434] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#A22828] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#A22828] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#e03f3f]">
            Buy on Solana
          </a>
          <a href="#"
            class="inline-flex items-center justify-center h-12 px-6 rounded-md text-white text-lg bg-gradient-to-tr from-[#ffe95a] to-[#afa734] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#A28D28] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#A28D28] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#e0b03f]">
            Chart on Dextools
          </a>
          <a href="#"
            class="inline-flex items-center justify-center h-12 px-6 rounded-md text-white text-lg bg-gradient-to-tr from-[#5affa4] to-[#34af57] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#28A23A] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#28A23A] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#3fe07b]">
            Join Telegram
          </a>
        </div>
      </div>
    </div>

  </div>
</template>

<style scoped>
/* Smooth animations */
.left-coin,
.right-coin {
  will-change: transform;
  animation: float 6s ease-in-out infinite;
}

/* Mobile responsiveness */
@media (max-width: 640px) {
  .left-coin {
    top: 10% !important;
    left: 3% !important;
    height: 60px !important;
  }

  .right-coin {
    top: 70% !important;
    right: 3% !important;
    height: 60px !important;
  }
}

@media (max-width: 768px) {
  .left-coin {
    top: 12% !important;
  }

  .right-coin {
    top: 65% !important;
  }
}

@keyframes float {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-10px);
  }
}
</style>
