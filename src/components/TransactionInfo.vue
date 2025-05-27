<script setup>
import { ref, onMounted } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'


// Register ScrollTrigger plugin
gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref(null)
const tokenRefs = []

const tokenomics = [
  {
    title: 'Total Supply',
    value: '1B',
    description: '$MERMEME Tokens',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="size-6">
            <path strokeLinecap="round" strokeLinejoin="round" d="m21 7.5-2.25-1.313M21 7.5v2.25m0-2.25-2.25 1.313M3 7.5l2.25-1.313M3 7.5l2.25 1.313M3 7.5v2.25m9 3 2.25-1.313M12 12.75l-2.25-1.313M12 12.75V15m0 6.75 2.25-1.313M12 21.75V19.5m0 2.25-2.25-1.313m0-16.875L12 2.25l2.25 1.313M21 14.25v2.25l-2.25 1.313m-13.5 0L3 16.5v-2.25" />
          </svg>
        `
  },
  {
    title: 'Liquidity',
    value: 'Locked',
    description: 'With DeFi',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="size-6">
          <path strokeLinecap="round" strokeLinejoin="round" d="M16.5 10.5V6.75a4.5 4.5 0 1 0-9 0v3.75m-.75 11.25h10.5a2.25 2.25 0 0 0 2.25-2.25v-6.75a2.25 2.25 0 0 0-2.25-2.25H6.75a2.25 2.25 0 0 0-2.25 2.25v6.75a2.25 2.25 0 0 0 2.25 2.25Z" />
        </svg>
        `
  },
  {
    title: 'Ownership',
    value: 'Renounced',
    description: 'No lifeguard on duty',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="size-6">
            <path strokeLinecap="round" strokeLinejoin="round" d="M18.364 18.364A9 9 0 0 0 5.636 5.636m12.728 12.728A9 9 0 0 1 5.636 5.636m12.728 12.728L5.636 5.636" />
          </svg>
          `
  },
  {
    title: 'Tax',
    value: '0%',
    description: 'Splash freely',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5} stroke="currentColor" className="size-6">
            <path strokeLinecap="round" strokeLinejoin="round" d="M2.25 18.75a60.07 60.07 0 0 1 15.797 2.101c.727.198 1.453-.342 1.453-1.096V18.75M3.75 4.5v.75A.75.75 0 0 1 3 6h-.75m0 0v-.375c0-.621.504-1.125 1.125-1.125H20.25M2.25 6v9m18-10.5v.75c0 .414.336.75.75.75h.75m-1.5-1.5h.375c.621 0 1.125.504 1.125 1.125v9.75c0 .621-.504 1.125-1.125 1.125h-.375m1.5-1.5H21a.75.75 0 0 0-.75.75v.75m0 0H3.75m0 0h-.375a1.125 1.125 0 0 1-1.125-1.125V15m1.5 1.5v-.75A.75.75 0 0 0 3 15h-.75M15 10.5a3 3 0 1 1-6 0 3 3 0 0 1 6 0Zm3 0h.008v.008H18V10.5Zm-12 0h.008v.008H6V10.5Z" />
          </svg>
          `
  }
]

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
  <div ref="sectionRef" class="bg-cyan-900 py-24 sm:py-32 overflow-hidden">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <div class="card">
        <div class="card-body space-y-12">
          <div class="commercial-text mb-4 flex justify-center sm:mb-8">
            <div
              class="relative rounded-full px-3 mb-5 py-1 text-xs font-semibold bg-[#910b9822] text-white ring-1 ring-purple-950 hover:ring-purple-500">
              🤑 Value
            </div>
          </div>
          <!-- Hero Section -->
          <div>
            <h1 class="text-center text-4xl font-bold uppercase text-white">
              experience seamless transactions with mermeme coin's minimal tax advantage
            </h1>
            <p class="text-center text-gray-300 mt-4">
              Mermeme Coin is a minimal tax token, allowing you to buy and sell without any additional fees.
              This means more value for you and your investments.
            </p>

            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-6">
              <div class="transactionType bg-white p-4 rounded-lg shadow-md flex items-center space-x-4">
                <svg class="w-10 h-10 text-green-700 text-bold" xmlns="http://www.w3.org/2000/svg" fill="none"
                  viewBox="0 0 24 24" stroke="currentColor">
                  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5}
                    stroke="currentColor" className="size-6">
                    <path strokeLinecap="round" strokeLinejoin="round"
                      d="M12 3v17.25m0 0c-1.472 0-2.882.265-4.185.75M12 20.25c1.472 0 2.882.265 4.185.75M18.75 4.97A48.416 48.416 0 0 0 12 4.5c-2.291 0-4.545.16-6.75.47m13.5 0c1.01.143 2.01.317 3 .52m-3-.52 2.62 10.726c.122.499-.106 1.028-.589 1.202a5.988 5.988 0 0 1-2.031.352 5.988 5.988 0 0 1-2.031-.352c-.483-.174-.711-.703-.59-1.202L18.75 4.971Zm-16.5.52c.99-.203 1.99-.377 3-.52m0 0 2.62 10.726c.122.499-.106 1.028-.589 1.202a5.989 5.989 0 0 1-2.031.352 5.989 5.989 0 0 1-2.031-.352c-.483-.174-.711-.703-.59-1.202L5.25 4.971Z" />
                  </svg>

                </svg>
                <div>
                  <h3 class="text-lg font-semibold">Transaction Type</h3>
                  <p>Buy / Sell</p>
                </div>
              </div>
              <div class="transactionFee bg-white p-4 rounded-lg shadow-md flex items-center space-x-4">
                <svg class="w-10 h-10 text-green-700 text-bold" xmlns="http://www.w3.org/2000/svg" fill="none"
                  viewBox="0 0 24 24" stroke="currentColor">
                  <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" strokeWidth={1.5}
                    stroke="currentColor" className="size-6">
                    <path strokeLinecap="round" strokeLinejoin="round"
                      d="M2.25 8.25h19.5M2.25 9h19.5m-16.5 5.25h6m-6 2.25h3m-3.75 3h15a2.25 2.25 0 0 0 2.25-2.25V6.75A2.25 2.25 0 0 0 19.5 4.5h-15a2.25 2.25 0 0 0-2.25 2.25v10.5A2.25 2.25 0 0 0 4.5 19.5Z" />
                  </svg>

                </svg>
                <div>
                  <h3 class="text-lg font-semibold">Transaction Fee</h3>
                  <p>0%</p>
                  <p class="text-sm text-gray-500">No additional fees on transactions</p>
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
                <svg class="w-10 h-10 mx-auto text-bold text-green-600 mb-2" xmlns="http://www.w3.org/2000/svg"
                  fill="none" viewBox="0 0 24 24" stroke="currentColor" v-html="item.icon">
                </svg>
                <h4 class="text-lg font-semibold">{{ item.title }}</h4>
                <p class="text-2xl font-bold text-green-900">{{ item.value }}</p>
                <p class="text-sm text-gray-600">{{ item.description }}</p>
              </div>
            </div>
          </div>

        </div>
      </div>
    </div>
  </div>
</template>
