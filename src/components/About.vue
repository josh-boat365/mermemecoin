<script setup>
import DextoolsLogo from '@/assets/imgs/dextools.webp'
import RaydiumLogo from '@/assets/imgs/raydium-ray.webp'
import CoinmarketcapLogo from '@/assets/imgs/coinmarketcap.webp'
import CoingeckoLogo from '@/assets/imgs/coingecko.webp'
import DexscreenerLogo from '@/assets/imgs/dexscreener.png'
import { ref, onMounted, onUnmounted } from 'vue'
import MermemeCommercial from '@/assets/vids/mermeme-commercial.mp4'
import VideoPoster from '@/assets/vids/poster.webp'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

// Register GSAP ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

const aboutSection = ref(null)

onMounted(() => {
  gsap.from(aboutSection.value, {
    scrollTrigger: {
      trigger: aboutSection.value,
      start: 'top 80%',
      toggleActions: 'play none none none',
    },
    opacity: 0,
    y: 40,
    duration: 1,
    ease: 'power2.out',
    immediateRender: false,
  })

  gsap.from(aboutSection.value.querySelectorAll('h2, p,.commercial-text, .video'), {
    scrollTrigger: {
      trigger: aboutSection.value,
      start: 'top 80%',
    },
    opacity: 0,
    y: 40,
    duration: 1,
    stagger: 0.3,
    ease: 'power2.out',
    immediateRender: false,
  })

  ScrollTrigger.refresh()
})




//Video control
const isVideoPlaying = ref(false)
const videoRef = ref(null)

const toggleVideo = () => {
  if (videoRef.value) {
    if (isVideoPlaying.value) {
      videoRef.value.pause()
    } else {
      videoRef.value.play()
    }
    isVideoPlaying.value = !isVideoPlaying.value
  }
}

</script>


<template>
  <div ref="aboutSection" class="bg-white py-16 sm:py-24" id="aboutSection">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">

          <div class="commercial-text mb-4 flex justify-center sm:mb-8">
            <div
              class="relative rounded-full px-3 mb-5 py-1 text-xs font-semibold bg-[#910b9822] text-purple-900 ring-1 ring-purple-950 hover:ring-purple-500">
              🍿🎥 Watch The Mermeme Coin Commercial
            </div>
          </div>
          
          <div class="flex flex-col lg:flex-row justify-between gap-y-24 gap-x-20">
            <!-- Text Section -->
            <div class="lg:w-1/2">
              <h2 class="text-3xl sm:text-4xl font-bold uppercase text-cyan-900 mb-4">
                What is Mermeme Coin?
              </h2>
              <p class="text-base text-justify sm:text-lg text-cyan-950">
                <strong>MERMEME</strong> is a community-driven meme coin on the Solana blockchain, designed to bring fun
                and
                engagement to the crypto space.
                With a focus on community participation, Mermeme Coin aims to create a vibrant ecosystem where users can
                enjoy memes, participate in events, and contribute to the growth of the project.
                The tokenomics are designed to ensure fair distribution and sustainability, making it an exciting
                opportunity for both meme enthusiasts and crypto investors.
              </p>
            </div>

            <!-- Video Container -->
            <div class="lg:w-1/2 w-full video">
              <div class="relative rounded-xl overflow-auto  aspect-video w-full">
                <video ref="videoRef" class="w-full h-full object-cover" :poster="VideoPoster" preload="metadata"
                  @click="toggleVideo" @play="isVideoPlaying = true" @pause="isVideoPlaying = false">
                  <source :src="MermemeCommercial" type="video/mp4" />
                  Your browser does not support the video tag.
                </video>

                <!-- Play button overlay -->
                <div v-if="!isVideoPlaying"
                  class="absolute inset-0 flex items-center justify-center cursor-pointer bg-black/1 hover:bg-black/10 transition-opacity duration-300"
                  @click="toggleVideo">
                  <div class="w-16 h-16 sm:w-20 sm:h-20 rounded-full flex items-center justify-center shadow-lg">
                    <svg xmlns="http://www.w3.org/2000/svg"
                      class="h-8 w-8 sm:h-10 sm:w-10 text-green-500 hover:text-white ml-1" viewBox="0 0 20 20"
                      fill="currentColor">
                      <path fill-rule="evenodd"
                        d="M10 18a8 8 0 100-16 8 8 0 000 16zM9.555 7.168A1 1 0 008 8v4a1 1 0 001.555.832l3-2a1 1 0 000-1.664l-3-2z"
                        clip-rule="evenodd" />
                    </svg>
                  </div>
                </div>
              </div>
            </div>

          </div>

    </div>
  </div>















  <!-- <div
        class="mx-auto mt-10 grid max-w-lg grid-cols-4 items-center gap-x-8 gap-y-10 sm:max-w-xl sm:grid-cols-6 sm:gap-x-10 lg:mx-0 lg:max-w-none lg:grid-cols-5">
        <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" :src="DextoolsLogo" alt="Dextools"
          width="158" height="48">
        <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" :src="RaydiumLogo" alt="Raydium"
          width="158" height="48">
        <img class="col-span-2 max-h-12 w-full object-contain lg:col-span-1" :src="CoinmarketcapLogo"
          alt="Coinmarketcap" width="158" height="48">
        <img class="col-span-2 max-h-12 w-full object-contain sm:col-start-2 lg:col-span-1" :src="CoingeckoLogo"
          alt="Coingecko" width="158" height="48">
        <img class="col-span-2 col-start-2 max-h-12 w-full object-contain sm:col-start-auto lg:col-span-1"
          :src="DexscreenerLogo" alt="Dexscreener" width="158" height="48">
      </div> -->
</template>
