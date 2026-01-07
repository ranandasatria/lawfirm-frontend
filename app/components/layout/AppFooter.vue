<template>
  <footer class="bg-slate-950 text-white pt-24 pb-12 border-t border-white/5">
    <div class="max-w-7xl mx-auto px-6">
      <div class="grid lg:grid-cols-12 gap-16 mb-20">
        <div class="lg:col-span-5">
          <div class="flex items-center gap-3 mb-8">
            <div class="w-10 h-10 bg-amber-500 rounded-xl flex items-center justify-center font-black text-slate-950 italic">M</div>
            <span class="font-bold text-2xl tracking-tighter uppercase">Merdiansyah <span class="text-amber-500">&</span> Partners</span>
          </div>
          <p class="text-slate-400 text-lg leading-relaxed mb-8 max-w-md italic">
            "Providing innovative and good legal solutions to our client. We work closely by our clients to handle their issues."
          </p>
        </div>

        <div class="lg:col-span-4">
          <h4 class="text-xs font-bold uppercase tracking-widest text-amber-500 mb-8">Kantor Pusat</h4>
          <p class="text-slate-300 leading-relaxed mb-6">
            Alamanda Tower, Lantai 2 - Suite H1<br>
            Jl. TB Simatupang Kav. 23-24, Cilandak Barat<br>
            Jakarta Selatan, DKI Jakarta 12430
          </p>
          <div class="space-y-2 text-sm">
            <p class="text-slate-400 flex items-center gap-2">
              <span class="text-amber-500">WA:</span> +62 822 1888 7115
            </p>
            <p class="text-slate-400 flex items-center gap-2">
              <span class="text-amber-500">Email:</span> budhy.m@mpartnerslawfirm.com
            </p>
          </div>
        </div>

        <div class="lg:col-span-3">
          <h4 class="text-xs font-bold uppercase tracking-widest text-amber-500 mb-8">Specialization</h4>
          <ul class="space-y-4 text-sm text-slate-400 font-medium">
            <li v-for="link in footerServices" :key="link.slug">
              <NuxtLink 
                :to="`/services/${link.slug}`" 
                class="hover:text-amber-500 hover:pl-2 transition-all duration-300 flex items-center gap-2"
              >
                <span class="text-[10px] opacity-0 group-hover:opacity-100">→</span>
                {{ link.title }}
              </NuxtLink>
            </li>
          </ul>
        </div>
      </div>

      <div class="pt-12 border-t border-white/5 flex flex-col md:flex-row justify-between items-center gap-6 text-xs text-slate-500 uppercase tracking-widest font-bold">
        <p>© 2026 Merdiansyah & Partners Law Firm. All Rights Reserved.</p>
        <!-- <div class="flex gap-8">
          <NuxtLink to="/privacy" class="hover:text-white transition">Privacy Policy</NuxtLink>
          <NuxtLink to="/terms" class="hover:text-white transition">Terms of Service</NuxtLink>
        </div> -->
      </div>
    </div>
  </footer>
</template>

<script setup>
const footerServices = [
  { title: 'Civil & Criminal Law', slug: 'civil-criminal' },
  { title: 'Intellectual Property', slug: 'ip-law' },
  { title: 'Corporate & Business', slug: 'corporate-law' },
  { title: 'Family & Divorce Law', slug: 'family-law' },
  { title: 'Taxation & Property', slug: 'tax-property' }
]
</script>