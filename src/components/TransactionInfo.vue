<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

import { Scale, WalletCards, Boxes, ShieldCheck, ShieldBan, HandCoins } from 'lucide-vue-next'



// Register ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref(null)
const tokenRefs = []

const tokenomics = [
  {
    title: 'Total Supply',
    value: '1B',
    description: '$MERMEME Tokens',
    icon: Boxes,
  },
  {
    title: 'Liquidity',
    value: 'Locked',
    description: 'With DeFi',
    icon: ShieldCheck,
  },
  {
    title: 'Ownership',
    value: 'Renounced',
    description: 'No lifeguard on duty',
    icon: ShieldBan,
  },
  {
    title: 'Token Utility',
    value: 'Simple',
    description: 'No complex fees',
    icon: HandCoins,
  }
];


onMounted(() => {
  gsap.from(tokenRefs, {
    scrollTrigger: {
      trigger: sectionRef.value,
      start: 'top 80%',
      toggleActions: 'play none none none'
    },
    opacity: 0,
    y: 40,
    duration: 1,
    stagger: 0.2,
    ease: 'power2.out',
    immediateRender: false
  })

  gsap.from(sectionRef.value.querySelectorAll('h1,h3,p, .transactionType, .transactionFee, .commercial-text'),{
    scrollTrigger: {
      trigger: sectionRef.value,
      start: 'top 80%',
      toggleActions: 'play none none none'
    },
    opacity: 0,
    y: 40,
    duration: 1,
    stagger: 0.2,
    ease: 'power2.out',
    immediateRender: false
  })

  ScrollTrigger.refresh()
})
</script>





<template>
  <div ref="sectionRef" class="bg-cyan-900 py-24 sm:py-32 overflow-hidden" id="tokenomicsSection">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="card">
        <div class="card-body space-y-12">

          <!-- Badge -->
          <div class="commercial-text mb-4 flex justify-center sm:mb-8">
            <div
              class="relative rounded-full px-3 mb-5 py-1 text-xs font-semibold bg-[#910b9822] text-white ring-1 ring-purple-950 hover:ring-purple-500">
              ⚡ Fast & Simple
            </div>

          </div>

          <!-- Hero Section -->
          <div>
            <h1 class="text-center text-4xl font-bold uppercase text-white">
              Experience Seamless Crypto Transactions with Mermeme Coin
            </h1>
            <p class="text-center text-gray-300 mt-4">
              Mermeme Coin is built for lightning-fast transactions and a smooth trading experience — designed for both
              new and seasoned users.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-6">
              <!-- Transaction Type -->
              <div class="transactionType bg-white p-4 rounded-lg shadow-md flex items-center space-x-4">
                <!-- <span class="material-symbols-outlined text-4xl text-cyan-600">currency_exchange</span> -->
                <Scale color="#0489b2" :size="40" :stroke-width="1" />
                <div>
                  <h3 class="text-lg font-semibold text-cyan-900">Transaction Type</h3>

                  <p class="text-cyan-950">Buy / Sell</p>
                </div>
              </div>

              <!-- Optimized Experience -->
              <div class="transactionFee bg-white p-4 rounded-lg shadow-md flex items-center space-x-4">
                <WalletCards color="#0489b2" :size="40" :stroke-width="1" />

                <div>
                  <h3 class="text-lg font-semibold">Optimized Experience</h3>
                  <p>Fast & Efficient</p>
                  <p class="text-sm text-gray-500">Designed to minimize delays and maximize usability</p>
                </div>
              </div>
            </div>
          </div>

          <!-- Mermenomics -->
          <div>
            <h2 class="text-center text-3xl font-bold text-white uppercase">Mermenomics</h2>
            <p class="text-center text-gray-300 mb-8">
              We dropped anchor on complications. Here's how we keep it simple.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6 text-center">
              <div class="bg-white p-5 rounded-lg shadow-lg" v-for="(item, index) in tokenomics" :key="index"
                :ref="el => tokenRefs[index] = el">
                <component :is="item.icon" color="#0489b2" :size="40" :stroke-width="1" class="mx-auto mb-2" />
                <h4 class="text-lg font-semibold">{{ item.title }}</h4>
                <p class="text-2xl font-bold ">{{ item.value }}</p>
                <p class="text-sm text-gray-600">{{ item.description }}</p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>

</template>
