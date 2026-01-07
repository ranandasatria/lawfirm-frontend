<template>
  <section class="py-24 bg-slate-50">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex justify-between items-end mb-12">
        <div>
          <h2 class="text-3xl font-bold text-slate-900 mb-2">Legal Insights</h2>
          <p class="text-slate-500">Edukasi hukum untuk perlindungan aset dan bisnis Anda.</p>
        </div>
        <NuxtLink to="/articles" class="px-6 py-2 border-2 border-slate-900 font-bold text-sm hover:bg-slate-900 hover:text-white transition">
          LIHAT SEMUA ARTIKEL
        </NuxtLink>
      </div>

      <div class="grid md:grid-cols-3 gap-8">
        <article v-for="post in featuredPosts" :key="post.slug" class="bg-white p-8 rounded-[2.5rem] border border-slate-200 hover:shadow-xl transition-all group flex flex-col">
          <div class="text-amber-600 font-bold text-[10px] mb-4 uppercase tracking-[0.2em]">{{ post.category }}</div>
          <h3 class="text-xl font-bold text-slate-900 mb-4 group-hover:text-amber-600 transition-colors leading-snug">
            {{ post.title }}
          </h3>
          <p class="text-slate-500 text-sm leading-relaxed mb-8 line-clamp-3">
            {{ post.excerpt }}
          </p>
          <div class="mt-auto flex justify-between items-center">
            <div class="font-bold text-[10px] text-slate-400 uppercase tracking-widest">— M&P EDITORIAL</div>
            <NuxtLink :to="`/articles/${post.slug}`" class="text-amber-600 font-bold text-xs hover:underline">BACA →</NuxtLink>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script setup>
const featuredPosts = [
  {
    title: 'Strategi Hukum Menghadapi Sengketa Tanah dan Sertifikat Ganda',
    slug: 'sengketa-tanah-solusi',
    category: 'Property',
    excerpt: 'Analisis mendalam mengenai perlindungan hak atas tanah, pembatalan sertifikat di PTUN, dan prosedur hukum menghadapi mafia tanah.'
  },
  {
    title: 'Cara Mendaftarkan Merek Dagang: Perlindungan Aset Intelektual',
    slug: 'panduan-daftar-merek',
    category: 'IP Law',
    excerpt: 'Panduan lengkap sistem First-to-File di Indonesia untuk mengamankan identitas bisnis Anda dari penyalahgunaan pihak ketiga.'
  },
  {
    title: 'Pentingnya Perjanjian Pra-Nikah dalam Perlindungan Aset Bisnis',
    slug: 'manfaat-perjanjian-pranikah',
    category: 'Family Law',
    excerpt: 'Bagaimana memisahkan harta pribadi dan aset perusahaan melalui Prenuptial Agreement untuk mitigasi risiko di masa depan.'
  }
]
</script>