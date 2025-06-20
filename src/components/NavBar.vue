<!-- src/components/NavBar.vue -->
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'
import MermemeLogo from '@/assets/imgs/mermeme-favicon.png'

const navigation = [
  { name: 'Home', href: '#home' },
  { name: 'About', href: '#aboutSection' },
  { name: 'Join Community', href: '#joinCommunity' },
  { name: 'Mermenomics', href: '#tokenomicsSection' },
]

const mobileMenuOpen = ref(false)
const isScrolled = ref(false)

// Handle scroll effect
const handleScroll = () => {
  isScrolled.value = window.scrollY > 10
}

// Add scroll event listener
onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

// Clean up event listener
onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header class="fixed inset-x-0 top-0 z-50 transition-all duration-300 ease-in-out" :class="{
      'glassy-effect bg-green-900/20 backdrop-blur-md border-b border-green-800/30 rounded-4xl mx-4 mt-3 shadow-lg': isScrolled,
      'bg-transparent': !isScrolled
    }">
    <nav class="flex items-center justify-between p-4 lg:px-8" aria-label="Global">
      <div class="flex lg:flex-1">
        <a href="#" class="-m-1.5 p-1.5">
          <span class="sr-only">Mermeme Coin</span>
          <span class="flex items-center gap-x-2">
            <img class="h-8 w-auto" :src="MermemeLogo" alt="" />
            <span class="text-white text-base font-semibold"> Mermeme
              Coin</span>
          </span>
        </a>
      </div>
      <div class="flex lg:hidden">
        <button type="button"
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-300 hover:bg-green-800/30 transition-colors"
          @click="mobileMenuOpen = true">
          <span class="sr-only">Open main menu</span>
          <Bars3Icon class="size-6" aria-hidden="true" />
        </button>
      </div>
      <div class="hidden lg:flex lg:gap-x-12">
        <a v-for="item in navigation" :key="item.name" :href="item.href"
          class="text-sm font-semibold text-white hover:text-green-400 transition-colors">{{ item.name }}</a>
      </div>
      <div class="hidden lg:flex lg:flex-1 lg:justify-end gap-3">
        <a href="#"
          class="text-sm font-semibold text-white px-4 py-1 border border-white rounded-3xl  hover:text-yellow-400 transition-colors">Sign
          in </a>
        <a href="#"
          class="text-sm font-semibold text-white bg-gradient-to-tr from-[#ff655a] to-[#af3434] rounded-3xl px-4 py-1 hover:text-white hover:bg-red-900 transition-colors">Sign
          up </a>
      </div>
    </nav>
    <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
      <div class="fixed inset-0 z-50" />
      <DialogPanel
        class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-cyan-900 px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-700/10">
        <div class="flex items-center justify-between">
          <a href="#" class="-m-1.5 p-1.5">
            <span class="sr-only">Mermeme Coin</span>
            <img class="h-8 w-auto" :src="MermemeLogo" alt="" />
          </a>
          <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-300 hover:bg-cyan-800/30"
            @click="mobileMenuOpen = false">
            <span class="sr-only">Close menu</span>
            <XMarkIcon class="size-6" aria-hidden="true" />
          </button>
        </div>
        <div class="mt-6 flow-root">
          <div class="-my-6 divide-y divide-cyan-800/50">
            <div class="space-y-2 py-6">
              <a v-for="item in navigation" :key="item.name" :href="item.href"
                class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold text-white hover:bg-cyan-800/30">{{
                item.name }}</a>
            </div>
            <div class="py-6">
              <a href="#"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold text-white hover:bg-cyan-800/30">Sign
                in</a>
              <a href="#"
                class="-mx-3 block rounded-lg px-3 py-2.5 text-base font-semibold text-white hover:bg-cyan-800/30">
                Sign up</a>
            </div>
          </div>
        </div>
      </DialogPanel>
    </Dialog>
  </header>
</template>
