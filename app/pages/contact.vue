<template>
  <div class="pt-40 pb-24 min-h-screen bg-white">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid lg:grid-cols-2 gap-20">
        
        <div>
          <h1 class="text-6xl font-bold text-slate-900 mb-8 tracking-tighter">Mulai Konsultasi.</h1>
          <p class="text-xl text-slate-600 mb-12 leading-relaxed">
            Penyelesaian masalah hukum Anda dimulai dengan satu langkah komunikasi. Hubungi Managing Partner kami langsung untuk respon cepat.
          </p>
          
          <div class="space-y-10">
            <div class="flex gap-6 group">
              <div class="w-14 h-14 bg-slate-900 rounded-2xl flex items-center justify-center flex-none group-hover:bg-amber-500 transition-colors duration-500">
                <span class="text-white group-hover:text-slate-900 transition-colors">📍</span>
              </div>
              <div>
                <h4 class="font-bold text-slate-900 text-lg uppercase tracking-widest text-xs mb-1">Kantor Pusat</h4>
                <p class="text-slate-600 font-medium">
                  Alamanda Tower, Lt. 2 - Suite H1<br>
                  Jl. TB Simatupang Kav. 23-24, Jakarta Selatan
                </p>
              </div>
            </div>

            <div class="flex gap-6 group">
              <div class="w-14 h-14 bg-slate-900 rounded-2xl flex items-center justify-center flex-none group-hover:bg-amber-500 transition-colors duration-500">
                <span class="text-white group-hover:text-slate-900 transition-colors">📞</span>
              </div>
              <div>
                <h4 class="font-bold text-slate-900 text-lg uppercase tracking-widest text-xs mb-1">WhatsApp & Call</h4>
                <p class="text-slate-600 font-medium">+62 8221 888 7115</p>
                <a href="https://wa.me/6282218887115" target="_blank" class="text-amber-600 font-bold text-sm hover:underline">Chat di WhatsApp Sekarang →</a>
              </div>
            </div>
          </div>
        </div>

        <div class="bg-slate-50 p-12 rounded-[3.5rem] border border-slate-100 shadow-sm">
          <h3 class="text-2xl font-bold text-slate-900 mb-8">Formulir Permohonan</h3>
          
          <form @submit.prevent="handleExternalContact" class="space-y-6">
            <div class="space-y-2">
              <label class="text-[10px] font-black uppercase tracking-[0.2em] text-slate-400">Nama Lengkap Anda</label>
              <input 
                v-model="form.name"
                type="text" 
                required
                class="w-full p-5 rounded-2xl border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-amber-500 outline-none transition bg-white text-slate-900" 
                placeholder="Contoh: Budi Santoso">
            </div>

            <div class="space-y-2">
              <label class="text-[10px] font-black uppercase tracking-[0.2em] text-slate-400">Pilih Jalur Komunikasi</label>
              <div class="grid grid-cols-2 gap-4">
                <button 
                  type="button" 
                  @click="method = 'email'"
                  :class="method === 'email' ? 'bg-slate-900 text-white' : 'bg-white text-slate-500'"
                  class="py-3 rounded-xl font-bold text-xs border border-slate-200 transition-all">
                  VIA EMAIL
                </button>
                <button 
                  type="button" 
                  @click="method = 'whatsapp'"
                  :class="method === 'whatsapp' ? 'bg-green-600 text-white border-green-600' : 'bg-white text-slate-500'"
                  class="py-3 rounded-xl font-bold text-xs border border-slate-200 transition-all">
                  VIA WHATSAPP
                </button>
              </div>
            </div>

            <div class="space-y-2">
              <label class="text-[10px] font-black uppercase tracking-[0.2em] text-slate-400">Ringkasan Masalah</label>
              <textarea 
                v-model="form.message"
                rows="5" 
                required
                class="w-full p-5 rounded-2xl border-none ring-1 ring-slate-200 focus:ring-2 focus:ring-amber-500 outline-none transition bg-white text-slate-900" 
                placeholder="Jelaskan secara singkat kasus yang ingin dikonsultasikan..."></textarea>
            </div>

            <button 
              type="submit"
              class="w-full py-5 bg-amber-500 text-slate-950 rounded-2xl font-black uppercase tracking-widest text-xs hover:bg-slate-900 hover:text-white transition-all transform hover:-translate-y-1 shadow-xl">
              Hubungi Pengacara Sekarang
            </button>
          </form>
          
          <!-- <p class="mt-6 text-center text-slate-400 text-[10px] uppercase tracking-widest leading-relaxed">
            Dengan menekan tombol, aplikasi eksternal akan terbuka <br> untuk mengirimkan pesan secara aman.
          </p> -->
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const method = ref('email')
const form = reactive({
  name: '',
  message: ''
})

const handleExternalContact = () => {
  const adminEmail = 'budhy.m@mpartnerslawfirm.com'
  const adminPhone = '6282218887115' 

  if (method.value === 'email') {
    const subject = encodeURIComponent(`Konsultasi Hukum: ${form.name}`)
    const body = encodeURIComponent(`Halo Merdiansyah & Partners,\n\nSaya ${form.name} ingin berkonsultasi mengenai:\n\n${form.message}\n\nTerima kasih.`)
    window.location.href = `mailto:${adminEmail}?subject=${subject}&body=${body}`
  } else {
    const text = encodeURIComponent(`Halo Merdiansyah & Partners, saya *${form.name}*.\n\nSaya ingin berkonsultasi mengenai:\n\n${form.message}`)
    window.open(`https://wa.me/${adminPhone}?text=${text}`, '_blank')
  }
}
</script>