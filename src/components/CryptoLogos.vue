<script setup>
import DextoolsLogo from '@/assets/imgs/dextools.webp'
import RaydiumLogo from '@/assets/imgs/raydium-ray.webp'
import CoinmarketcapLogo from '@/assets/imgs/coinmarketcap.webp'
import CoingeckoLogo from '@/assets/imgs/coingecko.webp'
import DexscreenerLogo from '@/assets/imgs/dexscreener.png'
</script>


<template>
  <div class="bg-white py-24 sm:py-32">
    <div class="mx-auto max-w-7xl px-6 lg:px-8">
      <h2 class="text-center text-4xl font-bold uppercase text-gray-900">You can Find Mermeme Coin on These Platforms
      </h2>
      <div
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
      </div>
    </div>
  </div>

</template>
