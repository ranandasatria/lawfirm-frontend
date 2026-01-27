<template>
  <section class="relative pt-40 pb-24 overflow-hidden bg-slate-950 text-white">
    <div class="absolute top-0 left-1/2 -translate-x-1/2 w-full h-full pointer-events-none">
      <div class="absolute top-[-10%] left-[-10%] w-[40%] h-[40%] bg-amber-600/10 rounded-full blur-[120px]"></div>
    </div>
    <div class="relative max-w-7xl mx-auto px-6 grid lg:grid-cols-12 gap-12 items-center">
      <div class="lg:col-span-7">
        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-amber-500/10 border border-amber-500/20 mb-8">
          <span class="text-xs font-bold text-amber-500 uppercase tracking-widest">Advokat & Konsultan Hukum</span>
        </div>
        <h1 class="text-5xl lg:text-7xl font-bold tracking-tight mb-8 leading-[1.1]">
          Solusi Hukum <span class="text-amber-500 bg-clip-text bg-linear-to-r from-amber-400 to-amber-600">Terpercaya.</span>
        </h1>
        <p class="text-xl text-slate-400 mb-10 leading-relaxed max-w-2xl">
          Kami memberikan solusi hukum inovatif yang dirancang khusus untuk melindungi kepentingan bisnis dan personal Anda.
        </p>
        <div class="flex flex-col sm:flex-row gap-4">
          <a href="https://wa.me/6282218887115" class="px-8 py-4 bg-amber-500 text-slate-950 rounded-xl font-bold hover:bg-amber-400 transition-all text-center shadow-lg shadow-amber-500/20">
            Konsultasi
          </a>
          <a href="services" class="px-8 py-4 bg-transparent border border-slate-700 rounded-xl font-bold hover:border-white transition-all text-center">
            Lihat Layanan
          </a>
        </div>
      </div>
      <div class="lg:col-span-5 relative">
        <div class="aspect-square bg-slate-900 border border-slate-800 rounded-[3rem] p-12 flex items-center justify-center text-center shadow-2xl relative overflow-hidden">
          <div class="absolute inset-0 bg-linear-to-br from-amber-500/5 to-transparent"></div>
          
          <div class="absolute inset-0 flex items-center justify-center opacity-15">
            <img
              src="/images/logo.png"
              alt="Merdiansyah & Partners"
              class="w-3/4 h-3/4 object-contain"
            />
          </div>
          
          <span class="text-amber-500 font-bold italic text-xl px-12 leading-relaxed relative z-10">
            "Providing innovative and good legal solutions to our clients"
          </span>
        </div>
      </div>
    </div>
  </section>
</template>