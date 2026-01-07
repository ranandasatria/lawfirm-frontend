<template>
  <div class="pt-40 pb-24 bg-white">
    <div class="max-w-7xl mx-auto px-6">
      <div class="mb-16">
        <h1 class="text-5xl font-bold text-slate-900 mb-6 tracking-tight">Edukasi Hukum</h1>
        <p class="text-xl text-slate-600 max-w-2xl">Insight mendalam mengenai regulasi dan tips hukum untuk Anda dan bisnis Anda.</p>
      </div>

      <div class="grid md:grid-cols-3 gap-10">
        <div v-for="post in posts" :key="post.slug" class="group cursor-pointer">
          <NuxtLink :to="`/articles/${post.slug}`">
            <div class="aspect-video bg-slate-100 rounded-[2rem] overflow-hidden mb-6 border border-slate-100 shadow-sm transition-all group-hover:shadow-xl">
              <div class="w-full h-full bg-slate-900 flex items-center justify-center text-amber-500 font-bold italic">M&P Insight</div>
            </div>
            <div class="flex gap-3 mb-4">
              <span class="text-[10px] font-bold px-2 py-1 bg-amber-100 text-amber-700 rounded uppercase tracking-wider">{{ post.category }}</span>
            </div>
            <h3 class="text-2xl font-bold text-slate-900 mb-3 group-hover:text-amber-600 transition-colors leading-tight">
              {{ post.title }}
            </h3>
            <p class="text-slate-500 mb-6 line-clamp-2 leading-relaxed">{{ post.excerpt }}</p>
            <span class="text-sm font-bold text-slate-900 border-b-2 border-amber-500 pb-1 group-hover:bg-amber-500 group-hover:text-white transition-all">Baca Selengkapnya</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const posts = [
  {
    title: 'Langkah Hukum Saat Mengalami Sengketa Tanah',
    slug: 'sengketa-tanah-solusi',
    category: 'Property',
    excerpt: 'Memahami proses mediasi hingga litigasi dalam mempertahankan hak atas tanah dan properti Anda.'
  },
  {
    title: 'Cara Mendaftarkan Merek Dagang di Indonesia',
    slug: 'panduan-daftar-merek',
    category: 'IP Law',
    excerpt: 'Panduan lengkap mengenai syarat, biaya, dan tahapan pendaftaran merek untuk UMKM dan Korporasi.'
  },
  {
    title: 'Pentingnya Perjanjian Pra-Nikah bagi Pasangan',
    slug: 'manfaat-perjanjian-pranikah',
    category: 'Family Law',
    excerpt: 'Mengenal aspek perlindungan aset melalui perjanjian pranikah dalam hukum keluarga di Indonesia.'
  }
]
</script>