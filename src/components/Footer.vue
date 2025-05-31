<script setup>
import MermemeLogo from '@/assets/imgs/mermeme-favicon.png'
import AyeyiTechLogo from '@/assets/imgs/AT-long-logo-white.png'

document.addEventListener('DOMContentLoaded', function () {
  const currentDate = new Date();
  const year = currentDate.getFullYear();
  document.querySelector('.currentDate').textContent = year;
});

document.addEventListener('DOMContentLoaded', function () {
  const currentDate = new Date();
  const year = currentDate.getFullYear();
  document.querySelector('.currentYear').textContent = year;
});

</script>
<template>

  <footer class="bg-[#022335] text-white">
    <div class="mx-auto max-w-7xl px-6 py-12 md:py-16">

      <!-- Top section: Links -->
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-5 gap-10">
        <!-- Footer column -->
        <div>

          <div class="flex items-center gap-3 mb-4">
            <img class="w-10 h-auto" :src="MermemeLogo" alt="Mermeme Coin Logo" />
            <span class="text-lg font-bold text-white">Mermeme Coin</span>
          </div>
          <p class="text-sm text-gray-300 mb-4">
            Mermeme Coin is a community-driven cryptocurrency designed to provide fast, secure, and low-cost
            transactions.
            Join us in revolutionizing the crypto space!
          </p>
        </div>

        <!-- Optional extra column (or leave empty on smaller screens) -->
        <div class="hidden lg:block"></div>

        <!-- Footer column -->
        <div>
          <h2 class="text-sm font-semibold text-cyan-500 mb-4 uppercase">Solution</h2>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="hover:text-cyan-500">Marketing</a></li>
            <li><a href="#" class="hover:text-cyan-500">Analytics</a></li>
            <li><a href="#" class="hover:text-cyan-500">Commerce</a></li>
            <li><a href="#" class="hover:text-cyan-500">Insights</a></li>
          </ul>
        </div>

        <!-- Footer column -->
        <div>
          <h2 class="text-sm font-semibold text-cyan-500 mb-4 uppercase">Support</h2>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="hover:text-cyan-500">Pricing</a></li>
            <li><a href="#" class="hover:text-cyan-500">Documentation</a></li>
            <li><a href="#" class="hover:text-cyan-500">Guides</a></li>
            <li><a href="#" class="hover:text-cyan-500">API Status</a></li>
          </ul>
        </div>

        <!-- Footer column -->
        <div>
          <h2 class="text-sm font-semibold text-cyan-500 mb-4 uppercase">Company</h2>
          <ul class="space-y-2 text-sm">
            <li><a href="#" class="hover:text-cyan-500">About</a></li>
            <li><a href="#" class="hover:text-cyan-500">Blog</a></li>
            <li><a href="#" class="hover:text-cyan-500">Jobs</a></li>
            <li><a href="#" class="hover:text-cyan-500">Press</a></li>
            <li><a href="#" class="hover:text-cyan-500">Partners</a></li>
          </ul>
        </div>


      </div>

      <!-- Divider -->
      <div class="mt-10 mb-6 border-t border-gray-700"></div>

      <!-- Bottom section: Copyright and Logo -->
      <div class="flex flex-col items-center justify-center gap-3 text-sm text-center">
        <p>
          © 2025 - <span class="currentYear"></span> Mermeme Coin. All rights reserved. |
          <a href="#" class="hover:text-cyan-500">Privacy Policy</a> |
          <a href="#" class="hover:text-cyan-500">Terms of Service</a>
        </p>
        <div class="flex flex-col sm:flex-row items-center gap-2">
          <span class="font-semibold text-xs text-white">Powered by</span>
          <a href="https://linkedin.com/in/josh-boat" target="_blank" class="inline-block">
            <img class="w-20" :src="AyeyiTechLogo" alt="Ayeyi Technologies Logo" />
          </a>
        </div>
      </div>
    </div>
  </footer>


</template>
