<template>
  <div class="pt-40 pb-24 min-h-screen bg-white" v-if="service">
    <div class="max-w-4xl mx-auto px-6">
      <NuxtLink to="/services" class="inline-flex items-center text-amber-600 font-bold mb-12 hover:gap-2 transition-all uppercase text-xs tracking-widest">
        <span>←</span> <span class="ml-2">Kembali ke Layanan</span>
      </NuxtLink>
      
      <div class="mb-12">
        <span class="text-amber-500 font-bold text-sm uppercase tracking-widest mb-4 block">Spesialisasi Hukum</span>
        <h1 class="text-5xl md:text-6xl font-bold text-slate-900 leading-tight">{{ service.title }}</h1>
      </div>

      <div class="prose prose-lg max-w-none">
        <p class="text-xl text-slate-600 leading-relaxed mb-12 border-l-4 border-amber-500 pl-8">
          {{ service.longDescription }}
        </p>

        <h3 class="text-2xl font-bold text-slate-900 mb-6">Cakupan Penanganan:</h3>
        <div class="grid md:grid-cols-2 gap-4 mb-16">
          <div v-for="point in service.points" :key="point" class="flex items-start gap-3 p-4 bg-slate-50 rounded-2xl border border-slate-100">
            <span class="text-amber-500 font-bold text-xl">✓</span>
            <span class="text-slate-700 font-medium">{{ point }}</span>
          </div>
        </div>

        <div class="p-10 bg-slate-950 rounded-[2.5rem] text-white">
          <h4 class="text-xl font-bold mb-4 text-amber-500 italic">"Dedicated to our profession without compromise."</h4>
          <p class="text-slate-400 mb-8">Hubungi kami untuk konsultasi awal mengenai kasus {{ service.title }} Anda.</p>
          <NuxtLink to="/contact" class="inline-block px-8 py-4 bg-white text-slate-950 font-bold rounded-xl hover:bg-amber-500 transition-colors">
            Jadwalkan Konsultasi
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const route = useRoute()
const serviceData = {
  'civil-criminal': {
    title: 'Civil & Criminal Law',
    longDescription: 'Merdiansyah & Partners memberikan pendampingan hukum yang tangguh untuk kasus pidana maupun perdata. Kami memahami bahwa setiap kasus memiliki sensitivitas tinggi, sehingga kami memastikan strategi pembelaan atau gugatan disusun berdasarkan analisis fakta yang tajam dan tanpa kompromi.',
    points: ['Sengketa Perdata & Wanprestasi', 'Pendampingan Pidana (Kepolisian - Pengadilan)', 'Perbuatan Melawan Hukum', 'Eksekusi Jaminan & Hutang Piutang']
  },
  'ip-law': {
    title: 'Intellectual Property Law',
    longDescription: 'Di era ekonomi kreatif, perlindungan ide adalah segalanya. Kami menangani pendaftaran merek dagang, hak cipta, desain industri, dan paten. Kami juga siap melakukan tindakan hukum jika terjadi pelanggaran atau penggunaan tanpa izin terhadap aset intelektual Anda.',
    points: ['Pendaftaran Merek & Hak Cipta', 'Sengketa Pelanggaran HAKI', 'Lisensi & Waralaba (Franchise)', 'Perlindungan Rahasia Dagang']
  },
  'corporate-law': {
    title: 'Corporate & Business Law',
    longDescription: 'Kami bertindak sebagai penasihat hukum bagi perusahaan untuk memastikan setiap langkah bisnis memiliki payung hukum yang kuat. Layanan kami mencakup pembuatan kontrak internasional, proses akuisisi, hingga penanganan perusahaan yang mengalami pailit.',
    points: ['Legal Due Diligence (Uji Tuntas)', 'Merger & Akuisisi Perusahaan', 'Penyusunan Kontrak Bisnis', 'Kepailitan & Penundaan Kewajiban Pembayaran Utang (PKPU)']
  },
  'family-law': {
    title: 'Family & Divorce Law',
    longDescription: 'Kami menangani urusan hukum keluarga dengan pendekatan yang manusiawi namun tetap tegas secara hukum. Fokus kami adalah mencapai resolusi terbaik bagi klien, terutama terkait hak asuh anak dan pembagian aset keluarga secara adil.',
    points: ['Proses Perceraian & Mediasi', 'Hak Asuh & Nafkah Anak', 'Pembagian Harta Gono-Gini', 'Legalitas Perkawinan & Adopsi']
  },
  'tax-property': {
    title: 'Taxation & Property Law',
    longDescription: 'Sengketa lahan dan urusan pajak seringkali menjadi beban berat bagi pemilik aset. Kami membantu penyelesaian sengketa tanah di BPN/Pengadilan serta memberikan opini hukum terkait struktur perpajakan agar klien terhindar dari sanksi hukum.',
    points: ['Sengketa Pertanahan & Real Estate', 'Banding & Gugatan Pajak', 'Opini Hukum Perpajakan Bisnis', 'Pengurusan Sertifikat & Izin Properti']
  }
}
const service = serviceData[route.params.slug]
</script>