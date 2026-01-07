<template>
  <nav class="fixed top-0 w-full z-50 px-6 py-4">
    <div class="max-w-7xl mx-auto bg-slate-950/90 backdrop-blur-md border border-white/10 rounded-2xl px-6 py-3 flex justify-between items-center shadow-2xl">
      <NuxtLink to="/" class="flex items-center gap-3 group">
        <div class="w-8 h-8 bg-amber-500 rounded-lg flex items-center justify-center font-black text-slate-950 italic group-hover:bg-white transition-colors">M</div>
        <span class="font-bold text-xl tracking-tighter text-white uppercase">
          Merdiansyah <span class="text-amber-500">&</span> Partners
        </span>
      </NuxtLink>
      
      <div class="hidden md:flex gap-8 text-[10px] font-bold text-slate-300 uppercase tracking-[0.2em]">
        <NuxtLink to="/about" class="hover:text-amber-500 transition">Tentang Kami</NuxtLink>
        <NuxtLink to="/services" class="hover:text-amber-500 transition">Layanan</NuxtLink>
        <NuxtLink to="/articles" class="hover:text-amber-500 transition">Artikel</NuxtLink>
        <NuxtLink to="/contact" class="hover:text-amber-500 transition">Kontak</NuxtLink>
      </div>

      <a href="https://wa.me/6282218887115" target="_blank" class="bg-[#25D366] text-white px-5 py-2.5 rounded-xl text-[10px] font-black uppercase tracking-tighter hover:bg-white hover:text-[#25D366] transition-all flex items-center gap-2 shadow-lg shadow-green-500/20">
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
          <path d="M13.601 2.326A7.854 7.854 0 0 0 7.994 0C3.627 0 .068 3.558.064 7.926c0 1.399.366 2.76 1.06 3.972L0 16l4.104-1.076A7.864 7.864 0 0 0 7.994 16c4.367 0 7.926-3.558 7.93-7.93A7.898 7.898 0 0 0 13.6 2.326zM7.994 14.521a6.573 6.573 0 0 1-3.356-.92l-.24-.144-2.494.654.666-2.433-.156-.251a6.56 6.56 0 0 1-1.007-3.505c0-3.626 2.957-6.584 6.591-6.584a6.56 6.56 0 0 1 4.66 1.931 6.557 6.557 0 0 1 1.928 4.66c-.004 3.639-2.961 6.592-6.592 6.592zm3.615-4.934c-.197-.099-1.17-.578-1.353-.646-.182-.065-.315-.099-.445.099-.133.197-.513.646-.627.775-.114.133-.232.148-.43.05-.197-.1-.836-.308-1.592-.985-.59-.525-.985-1.175-1.103-1.372-.114-.198-.011-.304.088-.403.089-.088.197-.232.296-.346.1-.114.133-.198.198-.33.065-.134.034-.248-.015-.347-.05-.099-.445-1.076-.612-1.47-.16-.389-.323-.335-.445-.34-.114-.007-.247-.007-.38-.007a.729.729 0 0 0-.529.247c-.182.198-.691.677-.691 1.654 0 .977.71 1.916.81 2.049.098.133 1.394 2.132 3.383 2.992.47.205.84.326 1.129.418.475.152.904.129 1.246.08.38-.058 1.171-.48 1.338-.943.164-.464.164-.86.114-.943-.049-.084-.182-.133-.38-.232z"/>
        </svg>
        KONSULTASI GRATIS
      </a>
    </div>
  </nav>
</template>