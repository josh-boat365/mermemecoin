<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'
import MermemeImage from '@/assets/imgs/mermeme.jpg'

gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref(null)

onMounted(() => {
  const section = sectionRef.value

  // Animate the whole section fade-in
  gsap.from(section, {
    scrollTrigger: {
      trigger: section,
      start: 'top 80%',
      toggleActions: 'play none none none',
    },
    opacity: 0,
    y: 40,
    duration: 1,
    ease: 'power2.out',
    immediateRender: false
  })

  // Animate individual elements inside the section
  gsap.from(section.querySelectorAll('h2, p, .commercial-text, .image, .btn'), {
    scrollTrigger: {
      trigger: section,
      start: 'top 85%',
    },
    opacity: 0,
    y: 30,
    duration: 1,
    stagger: 0.2,
    ease: 'power2.out',
    immediateRender: false
  })

  ScrollTrigger.refresh()
})
</script>


<template>
  <div ref="sectionRef" class="w-full" id="joinCommunity">
    <div class="mx-auto max-w-7xl py-10">

      <div class="commercial-text mt-15 flex justify-center">
        <div
          class="relative rounded-full px-3 py-1 text-xs font-semibold bg-[#910b9822] text-white ring-1 ring-purple-950 hover:ring-purple-500">
          🔥 Community Driven
        </div>
      </div>


      <div class="py-24 text-white flex flex-col md:flex-row items-center justify-center gap-16">

        <!-- Left Side - Image -->
        <div class="w-2/2 md:w-1/3 sm:w-1/3 lg:w-1/3 flex justify-center image">
          <img :src="MermemeImage" alt="Mermeme Preview" class="rounded-4xl max-w-full h-auto object-contain" />
        </div>

        <!-- Right Side - Text Content -->
        <div class="w-full md:w-1/2 text-center md:text-left space-y-4">
          <h2 class="text-3xl md:text-4xl text-center font-bold uppercase text-white">Join the Mermeme Community</h2>
          <p class="text-lg text-center">
            Dive into the sea of fun and freedom with <strong>minimal transaction fees</strong>.
            Be part of the wave on today!
          </p>

          <div class="mt-10 flex flex-wrap gap-y-6 items-center justify-center gap-x-6">
            <a href="https://t.me/mermemecoin" target="_blank"
              class="btn inline-flex items-center justify-center h-12 px-6  rounded-md text-lg bg-gradient-to-tr from-[#ff655a] to-[#af3434] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#A22828] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#A22828] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#e03f3f]">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 32 32">
                <path
                  d="M16,2c-7.732,0-14,6.268-14,14s6.268,14,14,14,14-6.268,14-14S23.732,2,16,2Zm6.489,9.521c-.211,2.214-1.122,7.586-1.586,10.065-.196,1.049-.583,1.401-.957,1.435-.813,.075-1.43-.537-2.218-1.053-1.232-.808-1.928-1.311-3.124-2.099-1.382-.911-.486-1.412,.302-2.23,.206-.214,3.788-3.472,3.858-3.768,.009-.037,.017-.175-.065-.248-.082-.073-.203-.048-.29-.028-.124,.028-2.092,1.329-5.905,3.903-.559,.384-1.065,.571-1.518,.561-.5-.011-1.461-.283-2.176-.515-.877-.285-1.574-.436-1.513-.92,.032-.252,.379-.51,1.042-.773,4.081-1.778,6.803-2.95,8.164-3.517,3.888-1.617,4.696-1.898,5.222-1.907,.116-.002,.375,.027,.543,.163,.142,.115,.181,.27,.199,.379,.019,.109,.042,.357,.023,.551Z"
                  fill-rule="evenodd" fill="white"></path>
              </svg> &nbsp;
              Join Telegram
            </a>
            <a href="#"
              class="btn inline-flex items-center justify-center h-12 px-6 rounded-md text-lg bg-gradient-to-tr from-[#ffe95a] to-[#afa734] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#A28D28] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#A28D28] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#e0b03f]">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 32 32">
                <path
                  d="M18.42,14.009L27.891,3h-2.244l-8.224,9.559L10.855,3H3.28l9.932,14.455L3.28,29h2.244l8.684-10.095,6.936,10.095h7.576l-10.301-14.991h0Zm-3.074,3.573l-1.006-1.439L6.333,4.69h3.447l6.462,9.243,1.006,1.439,8.4,12.015h-3.447l-6.854-9.804h0Z" fill="white">
                </path>
              </svg> &nbsp;
              Twitter - X
            </a>
            <a href="#"
              class="btn inline-flex items-center justify-center h-12 px-6 rounded-md text-lg bg-gradient-to-tr from-[#5affa4] to-[#34af57] shadow-[0_2px_4px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_rgba(58,65,111,0.5)] transition-all duration-150 ease-in-out hover:shadow-[0_4px_8px_rgba(45,35,66,0.4),0_7px_13px_-3px_rgba(45,35,66,0.3),0_-3px_0_inset_#28A23A] hover:-translate-y-0.5 active:shadow-[inset_0_3px_7px_#28A23A] active:translate-y-0.5 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-[#3fe07b]">
              <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 32 32">
                <path fill="white"
                  d="M26.413,6.536c-1.971-.902-4.052-1.543-6.189-1.904-.292,.523-.557,1.061-.793,1.612-2.277-.343-4.592-.343-6.869,0-.236-.551-.5-1.089-.793-1.612-2.139,.365-4.221,1.006-6.194,1.909C1.658,12.336,.596,17.987,1.127,23.558h0c2.294,1.695,4.861,2.984,7.591,3.811,.615-.827,1.158-1.704,1.626-2.622-.888-.332-1.744-.741-2.56-1.222,.215-.156,.425-.316,.628-.472,4.806,2.26,10.37,2.26,15.177,0,.205,.168,.415,.328,.628,.472-.817,.483-1.676,.892-2.565,1.225,.467,.918,1.011,1.794,1.626,2.619,2.732-.824,5.301-2.112,7.596-3.808h0c.623-6.461-1.064-12.06-4.46-17.025Zm-15.396,13.596c-1.479,0-2.702-1.343-2.702-2.994s1.18-3.006,2.697-3.006,2.73,1.354,2.704,3.006-1.192,2.994-2.699,2.994Zm9.967,0c-1.482,0-2.699-1.343-2.699-2.994s1.18-3.006,2.699-3.006,2.723,1.354,2.697,3.006-1.189,2.994-2.697,2.994Z">
                </path>
              </svg> &nbsp;
              Join Discord
            </a>
          </div>
        </div>
      </div>

    </div>
  </div>
</template>
