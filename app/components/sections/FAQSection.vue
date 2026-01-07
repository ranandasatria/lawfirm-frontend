<template>
  <section class="py-24 bg-white">
    <div class="max-w-4xl mx-auto px-6">
      <div class="text-center mb-16">
        <h2 class="text-4xl font-bold text-slate-900 mb-4">Pertanyaan Umum</h2>
        <p class="text-slate-600 text-lg">Segala hal yang perlu Anda ketahui tentang memulai langkah hukum bersama kami.</p>
      </div>

      <div class="space-y-4">
        <div v-for="(faq, index) in faqs" :key="index" class="border border-slate-200 rounded-2xl overflow-hidden">
          <button 
            @click="activeFaq = activeFaq === index ? null : index"
            class="w-full p-6 text-left flex justify-between items-center bg-white hover:bg-slate-50 transition-colors"
          >
            <span class="font-bold text-slate-900">{{ faq.question }}</span>
            <span class="text-2xl text-slate-400">{{ activeFaq === index ? '−' : '+' }}</span>
          </button>
          <div 
            v-show="activeFaq === index"
            class="p-6 pt-0 text-slate-600 leading-relaxed bg-white"
          >
            {{ faq.answer }}
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const activeFaq = ref(0)
const faqs = [
  { 
    question: "Bagaimana cara memulai konsultasi dengan Merdiansyah & Partners?", 
    answer: "Anda dapat menghubungi kami melalui WhatsApp atau Email untuk menjadwalkan sesi konsultasi awal. Kami akan melakukan review singkat terhadap dokumen atau ringkasan kasus Anda sebelum pertemuan dilakukan." 
  },
  { 
    question: "Apakah ada biaya untuk konsultasi pertama?", 
    answer: "Kami menyediakan sesi analisis awal secara singkat untuk menentukan apakah kasus Anda masuk dalam cakupan layanan kami. Untuk konsultasi hukum mendalam dan legal opinion secara tertulis, akan dikenakan biaya profesional yang akan diinformasikan sebelumnya." 
  },
  { 
    question: "Berapa lama waktu yang dibutuhkan untuk menangani satu kasus?", 
    answer: "Durasi sangat bergantung pada kompleksitas kasus dan jalur yang ditempuh (litigasi atau non-litigasi). Namun, kami berkomitmen untuk memberikan update rutin agar prosesnya tetap transparan dan terukur." 
  },
  { 
    question: "Apakah firma menangani pendaftaran HAKI dan sengketa industri?", 
    answer: "Ya, kami memiliki divisi khusus untuk Corporate Law yang menangani pendaftaran Merek (Trademark), Paten, Hak Cipta, hingga urusan industrial dan kepailitan." 
  }
]
</script>