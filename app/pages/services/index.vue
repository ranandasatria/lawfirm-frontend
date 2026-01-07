<template>
  <div class="pt-32 pb-24">
    <div class="max-w-7xl mx-auto px-6">
      <h1 class="text-5xl font-bold text-slate-900 mb-6">Layanan Hukum Kami</h1>
      <p class="text-xl text-slate-600 max-w-3xl mb-16">
        Merdiansyah & Partners menyediakan spektrum layanan hukum yang luas, mulai dari bantuan hukum personal hingga konsultasi korporasi strategis.
      </p>

      <div class="grid md:grid-cols-2 gap-8">
        <div v-for="service in allServices" :key="service.slug" class="p-10 border border-slate-200 rounded-[2.5rem] hover:border-amber-500 transition-all group bg-slate-50">
          <h3 class="text-2xl font-bold mb-4 group-hover:text-amber-600 transition-colors">{{ service.title }}</h3>
          <p class="text-slate-600 mb-8 leading-relaxed">{{ service.description }}</p>
          <NuxtLink :to="`/services/${service.slug}`" class="font-bold text-amber-600 flex items-center gap-2">
            Pelajari Selengkapnya <span class="group-hover:translate-x-2 transition-transform">→</span>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const allServices = [
  { 
    title: 'Civil & Criminal Law', 
    slug: 'civil-criminal', 
    description: 'Penanganan kasus hukum perdata dan pidana secara komprehensif, mulai dari sengketa kontrak hingga pendampingan di kepolisian.' 
  },
  { 
    title: 'Intellectual Property Law', 
    slug: 'ip-law', 
    description: 'Perlindungan Hak Kekayaan Intelektual (HAKI) termasuk pendaftaran merek, hak cipta, dan paten untuk mengamankan aset bisnis Anda.' 
  },
  { 
    title: 'Corporate & Business Law', 
    slug: 'corporate-law', 
    description: 'Layanan hukum strategis untuk korporasi, merger & akuisisi, legal due diligence, serta penanganan kepailitan (insolvency).' 
  },
  { 
    title: 'Family & Divorce Law', 
    slug: 'family-law', 
    description: 'Solusi hukum privat untuk urusan keluarga, perceraian, hak asuh anak, hingga pembagian harta gono-gini dengan kerahasiaan tinggi.' 
  },
  { 
    title: 'Taxation & Property Law', 
    slug: 'tax-property', 
    description: 'Konsultasi hukum perpajakan dan penyelesaian sengketa pertanahan atau real estate secara prosedural dan sah.' 
  }
]
</script>