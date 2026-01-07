<template>
  <section class="py-24 bg-white border-y border-slate-100">
    <div class="max-w-7xl mx-auto px-6">
      <div class="text-center max-w-3xl mx-auto mb-20">
        <h2 class="text-4xl font-bold text-slate-900 mb-4">Metodologi M&P</h2>
        <p class="text-slate-600 italic">"Handling issues with time to time and always keeping you updated."</p>
      </div>

      <div class="grid md:grid-cols-4 gap-12 relative">
        <div class="hidden md:block absolute top-10 left-0 w-full h-[2px] bg-amber-100 -z-10"></div>
        
        <div v-for="(step, index) in steps" :key="index" class="group">
          <div class="w-20 h-20 bg-slate-950 rounded-2xl flex items-center justify-center text-2xl font-black text-amber-500 mb-6 group-hover:bg-amber-500 group-hover:text-slate-950 transition-all shadow-lg">
            0{{ index + 1 }}
          </div>
          <h3 class="font-bold text-xl mb-3 text-slate-900">{{ step.title }}</h3>
          <p class="text-slate-500 text-sm leading-relaxed">{{ step.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const steps = [
  { 
    title: 'Legal Intake', 
    desc: 'Review mendalam terhadap kasus Law Cases atau Corporate Cases untuk memahami detail tanpa kompromi.' 
  },
  { 
    title: 'Skilled Appointment', 
    desc: 'Kami menunjuk satu pengacara yang paling ahli dan terlatih khusus untuk menangani isu spesifik Anda.' 
  },
  { 
    title: 'Innovative Solution', 
    desc: 'Pemberian opini hukum dan strategi yang inovatif, baik untuk urusan litigasi maupun dokumentasi.' 
  },
  { 
    title: 'Continuous Update', 
    desc: 'Pendampingan secara intensif dari waktu ke waktu dan pelaporan progress secara berkala kepada klien.' 
  }
]
</script>