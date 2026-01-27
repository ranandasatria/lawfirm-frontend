<template>
  <nav class="fixed top-0 w-full z-50 px-3 sm:px-4 lg:px-6 py-3 sm:py-4">
    <div class="max-w-7xl mx-auto bg-slate-950/90 backdrop-blur-md border border-white/10 rounded-2xl px-4 sm:px-5 lg:px-6 py-3 sm:py-3.5 flex items-center justify-between shadow-2xl shadow-black/20 transition-all duration-300 hover:shadow-amber-500/5">
      
      <!-- Logo -->
      <NuxtLink 
        to="/" 
        class="flex items-center gap-2 sm:gap-3 group relative"
        @click="closeMenu"
      >
        <img
          src="/images/logo.png"
          alt="Merdiansyah & Partners"
          class="w-32 h-32 sm:w-16 sm:h-16 object-contain"
        />

        <span class="font-bold text-sm sm:text-base lg:text-xl tracking-tight text-white uppercase group-hover:text-amber-400 transition-colors duration-300">
          Merdiansyah <span class="text-amber-500">&</span> Partners
        </span>
      </NuxtLink>
      
      <!-- Desktop Navigation -->
      <div class="hidden lg:flex items-center gap-8 xl:gap-10">
        <NuxtLink 
          v-for="link in navLinks" 
          :key="link.path"
          :to="link.path" 
          class="relative text-[10px] xl:text-[11px] font-bold text-slate-300 uppercase tracking-[0.15em] hover:text-white transition-colors duration-300 group py-1"
        >
          {{ link.name }}
          <span class="absolute bottom-0 left-0 w-0 h-0.5 bg-gradient-to-r from-amber-500 to-amber-300 group-hover:w-full transition-all duration-300"></span>
        </NuxtLink>
      </div>

      <!-- CTA & Mobile Toggle -->
      <div class="flex items-center gap-3 sm:gap-4">
        <!-- WhatsApp Button -->
        <a 
          href="https://wa.me/6282218887115" 
          target="_blank"
          rel="noopener noreferrer"
          class="group relative bg-gradient-to-r from-[#25D366] to-[#128C7E] text-white px-4 sm:px-5 lg:px-6 py-2 sm:py-2.5 rounded-xl text-[9px] sm:text-[10px] font-black uppercase tracking-tight hover:shadow-lg hover:shadow-green-500/40 transition-all duration-300 flex items-center gap-2 overflow-hidden"
        >
          <span class="absolute inset-0 bg-white opacity-0 group-hover:opacity-20 transition-opacity duration-300"></span>
          <svg class="w-3.5 h-3.5 sm:w-4 sm:h-4 relative z-10 group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 16 16">
            <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.06 3.972L0 16l4.104-1.076A7.864 7.864 0 0 0 7.994 16c4.367 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.089-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
          </svg>
          <span class="relative z-10 hidden sm:inline">Konsultasi</span>
        </a>

        <!-- Hamburger Button -->
        <button
          @click="toggleMenu"
          class="lg:hidden relative w-10 h-10 flex items-center justify-center text-white hover:text-amber-400 transition-colors duration-300 focus:outline-none focus:ring-2 focus:ring-amber-500/50 rounded-lg"
          :aria-label="isMenuOpen ? 'Tutup menu' : 'Buka menu'"
          :aria-expanded="isMenuOpen"
        >
          <div class="w-5 h-4 flex flex-col justify-between">
            <span 
              class="w-full h-0.5 bg-current rounded-full transition-all duration-300 origin-left"
              :class="isMenuOpen ? 'rotate-45 translate-y-[-1px]' : ''"
            ></span>
            <span 
              class="w-full h-0.5 bg-current rounded-full transition-all duration-300"
              :class="isMenuOpen ? 'opacity-0 scale-0' : 'opacity-100 scale-100'"
            ></span>
            <span 
              class="w-full h-0.5 bg-current rounded-full transition-all duration-300 origin-left"
              :class="isMenuOpen ? '-rotate-45 translate-y-[1px]' : ''"
            ></span>
          </div>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 -translate-y-4 scale-95"
      enter-to-class="opacity-100 translate-y-0 scale-100"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0 scale-100"
      leave-to-class="opacity-0 -translate-y-4 scale-95"
    >
      <div 
        v-show="isMenuOpen"
        class="lg:hidden mt-3 mx-3 sm:mx-4 bg-slate-950/95 backdrop-blur-xl border border-white/10 rounded-2xl p-5 sm:p-6 shadow-2xl shadow-black/40"
      >
        <div class="flex flex-col gap-1">
          <NuxtLink 
            v-for="(link, index) in navLinks" 
            :key="link.path"
            :to="link.path"
            @click="closeMenu"
            class="group relative px-4 py-3.5 text-xs sm:text-sm font-bold text-slate-300 uppercase tracking-wide hover:text-white transition-all duration-300 rounded-xl hover:bg-white/5"
            :style="{ transitionDelay: `${index * 30}ms` }"
          >
            <span class="relative z-10">{{ link.name }}</span>
            <span class="absolute left-0 top-1/2 -translate-y-1/2 w-1 h-0 bg-gradient-to-b from-amber-400 to-amber-600 rounded-full group-hover:h-8 transition-all duration-300"></span>
          </NuxtLink>
        </div>
        
        <div class="mt-5 pt-5 border-t border-white/5">
          <a 
            href="https://wa.me/6282218887115"
            target="_blank"
            rel="noopener noreferrer"
            class="flex items-center justify-center gap-3 w-full bg-gradient-to-r from-[#25D366] to-[#128C7E] text-white py-4 rounded-xl text-xs sm:text-sm font-black uppercase tracking-wide hover:shadow-lg hover:shadow-green-500/40 transition-all duration-300 group"
          >
            <svg class="w-5 h-5 group-hover:scale-110 transition-transform duration-300" fill="currentColor" viewBox="0 0 16 16">
              <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.06 3.972L0 16l4.104-1.076A7.864 7.864 0 0 0 7.994 16c4.367 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.089-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
            </svg>
            WhatsApp Kami
          </a>
        </div>
      </div>
    </Transition>
  </nav>
</template>

<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const navLinks = [
  { name: 'Tentang Kami', path: '/about' },
  { name: 'Layanan', path: '/services' },
  { name: 'Artikel', path: '/articles' },
  { name: 'Kontak', path: '/contact' }
]

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>