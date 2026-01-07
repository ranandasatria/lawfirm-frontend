<template>
  <div class="pt-40 pb-24 bg-white min-h-screen" v-if="post">
    <div class="max-w-4xl mx-auto px-6">
      <NuxtLink to="/articles" class="text-amber-600 font-bold uppercase tracking-widest text-xs mb-10 inline-block">← KEMBALI KE EDUKASI HUKUM</NuxtLink>
      
      <header class="mb-16">
        <span class="text-amber-500 font-bold text-sm uppercase tracking-[0.3em] mb-4 block">{{ post.category }}</span>
        <h1 class="text-4xl md:text-6xl font-bold text-slate-900 leading-[1.1] mb-10 tracking-tight">{{ post.title }}</h1>
        <div class="flex items-center gap-6 border-t border-slate-100 pt-8">
           <div class="w-14 h-14 bg-slate-900 rounded-2xl flex items-center justify-center font-black text-amber-500 italic text-2xl">M</div>
           <div>
             <p class="text-slate-900 font-bold text-lg">Budhy Merdiansyah, S.H., M.M.</p>
             <p class="text-slate-400 text-sm italic">Managing Partner at Merdiansyah & Partners</p>
           </div>
        </div>
      </header>

      <article class="prose prose-xl prose-slate max-w-none 
        prose-p:text-slate-600 prose-p:leading-[2.1] prose-p:mb-10 prose-p:text-justify prose-p:indent-10
        prose-h3:text-3xl prose-h3:font-bold prose-h3:text-slate-900 prose-h3:mt-16 prose-h3:mb-8
        prose-strong:text-slate-900 prose-strong:font-extrabold
        prose-li:text-slate-600 prose-li:mb-4"
        v-html="post.content">
      </article>

      <div class="mt-24 p-12 bg-slate-950 rounded-[3.5rem] text-center border-t-8 border-amber-500">
        <h4 class="text-3xl font-bold text-white mb-6">Butuh Penanganan Kasus Spesifik?</h4>
        <p class="text-slate-400 text-lg mb-10 max-w-2xl mx-auto">Informasi di atas adalah edukasi hukum umum. Setiap masalah hukum memiliki detail yang unik. Konsultasikan isu Anda secara mendalam dengan pengacara kami.</p>
        <NuxtLink to="/contact" class="inline-block bg-amber-500 text-slate-950 px-12 py-5 rounded-2xl font-bold hover:bg-white transition-all shadow-2xl">Jadwalkan Konsultasi Sekarang</NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
const route = useRoute()

const postsData = {
  'sengketa-tanah-solusi': {
    title: 'Strategi Hukum Menghadapi Sengketa Tanah dan Fenomena Sertifikat Ganda',
    category: 'Property Law',
    content: `
      <p>Sengketa tanah di Indonesia merupakan persoalan hukum yang memiliki kompleksitas sangat tinggi, seringkali melibatkan irisan antara hukum perdata, hukum administrasi negara, bahkan hukum pidana. Fenomena sertifikat ganda (overlapping) menjadi momok yang menakutkan bagi kepastian hukum hak atas tanah. Merdiansyah & Partners seringkali menangani kasus di mana klien yang telah menguasai tanah selama puluhan tahun tiba-tiba menghadapi klaim dari pihak lain yang juga memegang sertifikat sah keluaran BPN.</p>

      <h3>Memahami Kedudukan Hukum Sertifikat Tanah</h3>
      <p>Berdasarkan Peraturan Pemerintah Nomor 24 Tahun 1997 tentang Pendaftaran Tanah, sertifikat adalah alat pembuktian yang kuat, namun perlu digarisbawahi bahwa sistem pendaftaran tanah kita menganut publikasi negatif berunsur positif. Hal ini berarti negara tidak menjamin mutlak kebenaran data dalam sertifikat. Jika pihak lain dapat membuktikan adanya <strong>Cacat Hukum Administratif</strong> dalam penerbitan sertifikat tersebut—seperti pemalsuan warkah, prosedur ukur yang salah, atau tumpang tindih lahan—maka sertifikat tersebut dapat dibatalkan melalui Pengadilan Tata Usaha Negara (PTUN).</p>

      <h3>Analisis Kekuatan Pembuktian di Persidangan</h3>
      <p>Dalam sengketa pertanahan, hakim tidak hanya melihat siapa yang memiliki sertifikat terbaru, melainkan siapa yang memiliki <strong>Dasar Hak (History of Title)</strong> yang paling benar. Pembuktian akan ditarik mundur hingga ke warkah tanah asli, girik, atau Letter C. Penguasaan fisik tanah secara terus-menerus selama lebih dari 20 tahun dengan itikad baik (<em>Rechtverwerking</em>) juga menjadi poin krusial yang kami perjuangkan bagi klien kami di pengadilan.</p>

      <h3>Penanganan Kasus Mafia Tanah</h3>
      <p>Kami menyadari bahwa praktik mafia tanah seringkali melibatkan oknum yang memalsukan dokumen otentik. Merdiansyah & Partners bekerja sama dengan ahli forensik dokumen untuk membedah keabsahan surat-surat tanah. Langkah yang kami ambil tidak hanya terbatas pada gugatan perdata untuk mempertahankan lahan, tetapi juga laporan pidana terkait Pasal 263 KUHP tentang pemalsuan surat guna memberikan perlindungan maksimal bagi kepentingan hukum klien.</p>
      
      <p>Kesimpulannya, menghadapi sengketa tanah memerlukan ketelitian dalam melacak sejarah tanah dan ketegasan dalam mengambil tindakan hukum administratif. Penundaan tindakan hukum hanya akan memperlemah posisi tawar dan hak penguasaan Anda di mata hukum.</p>
    `
  },
  'panduan-daftar-merek': {
    title: 'Panduan Strategis Perlindungan Merek: Mengamankan Goodwill Bisnis Anda',
    category: 'IP Law',
    content: `
      <p>Di era digital dan kompetisi global, merek bukan lagi sekadar nama, melainkan aset tak berwujud (intangible asset) yang paling berharga bagi sebuah perusahaan. Banyak pengusaha baru menyadari pentingnya hukum merek setelah identitas bisnis mereka ditiru atau bahkan didaftarkan oleh pihak lain yang beritikad buruk. Indonesia secara tegas menganut sistem <strong>First-to-File</strong>, sebuah prinsip di mana negara memberikan perlindungan hukum eksklusif hanya kepada pihak yang pertama kali mengajukan pendaftaran, bukan yang pertama kali menggunakan.</p>

      <h3>Risiko Fatal Tanpa Perlindungan HAKI</h3>
      <p>Bayangkan Anda telah membangun reputasi bisnis selama bertahun-tahun, mengeluarkan biaya pemasaran yang besar, namun tiba-tiba menerima surat somasi pelanggaran merek dari pihak lain yang baru berdiri namun sudah memegang sertifikat merek dari DJKI. Anda bisa dipaksa secara hukum untuk mengganti seluruh nama bisnis, menghancurkan stok produk, hingga membayar ganti rugi materiil yang dapat membangkrutkan perusahaan. Inilah mengapa pendaftaran merek adalah langkah <em>mitigasi risiko</em> yang tidak boleh ditawar.</p>

      <h3>Proses Pemeriksaan Substantif dan Strategi Sanggahan</h3>
      <p>Pendaftaran merek melibatkan fase pemeriksaan substantif yang ketat oleh pemeriksa DJKI. Banyak permohonan ditolak karena dianggap memiliki <strong>Persamaan Pada Pokoknya</strong> dengan merek terdaftar lain. Di Merdiansyah & Partners, kami tidak hanya sekadar mendaftarkan; kami melakukan penelusuran mendalam (<em>clearing search</em>) sebelum aplikasi diajukan. Jika terjadi usulan penolakan, kami menyusun tanggapan hukum substantif yang berargumen pada perbedaan visual, fonetik, dan konseptual untuk memastikan merek klien kami tetap dapat terbit sertifikatnya.</p>

      <h3>Pemanfaatan Merek sebagai Instrumen Komersial</h3>
      <p>Selain fungsi perlindungan, merek yang terdaftar memiliki nilai ekonomi yang dapat dijaminkan, dilisensikan, atau dijadikan dasar untuk skema waralaba (franchise). Kami membantu klien menyusun kontrak lisensi yang kuat guna memastikan royalti dan kualitas merek tetap terjaga. Investasi pada legalitas merek hari ini adalah cara terbaik menjamin keberlanjutan bisnis di masa depan.</p>
    `
  },
  'manfaat-perjanjian-pranikah': {
    title: 'Relevansi Perjanjian Perkawinan (Prenuptial) bagi Pemilik Bisnis dan Profesional',
    category: 'Family Law',
    content: `
      <p>Perjanjian perkawinan seringkali dianggap sebagai bentuk ketidaksiapan untuk berkomitmen, namun dalam perspektif hukum modern, hal ini adalah bentuk tanggung jawab finansial yang dewasa. Bagi seorang pengusaha atau pemilik bisnis, menikah tanpa perjanjian pemisahan harta berarti mencampuradukkan aset perusahaan dengan harta bersama. Hal ini membawa risiko besar: jika perkawinan berakhir dengan perceraian, kelangsungan operasional perusahaan dapat terganggu karena adanya tuntutan pembagian harta gono-gini atas saham perusahaan.</p>

      <h3>Pemisahan Hutang dan Perlindungan Keluarga</h3>
      <p>Salah satu manfaat utama yang sering terlupakan dari Perjanjian Pranikah (Prenup) atau Perjanjian Pasca-Nikah (Postnup) adalah <strong>Pemisahan Hutang</strong>. Jika salah satu pasangan melakukan perikatan hutang piutang untuk bisnis atau kepentingan pribadi, maka harta pasangan lainnya tidak dapat disita oleh kreditur. Ini memberikan jaring pengaman bagi keluarga agar jika terjadi kegagalan bisnis di salah satu pihak, aset rumah tangga dan aset pasangan tetap aman dan terlindungi.</p>

      <h3>Konsekuensi Putusan MK No. 69/2015</h3>
      <p>Dahulu, perjanjian ini harus dibuat sebelum ijab kabul atau pemberkatan. Namun, setelah Putusan Mahkamah Konstitusi No. 69/PUU-XIII/2015, pasangan yang sudah menikah pun dapat membuat perjanjian pemisahan harta melalui akta notaris. Hal ini sangat membantu bagi pasangan yang baru menyadari pentingnya legalitas aset setelah bisnis mereka berkembang pesat di tengah masa pernikahan.</p>

      <h3>Penyusunan Draf yang Berkeadilan</h3>
      <p>Merdiansyah & Partners membantu menyusun klausul perjanjian yang tidak hanya melindungi aset, tetapi juga tetap menjamin hak-hak pasangan dan anak di masa depan. Perjanjian yang baik haruslah adil, transparan, dan memenuhi syarat formil agar tidak mudah dibatalkan di pengadilan agama atau pengadilan negeri di kemudian hari. Kami memastikan setiap kata dalam perjanjian tersebut memiliki kekuatan eksekutorial yang pasti.</p>
    `
  }
}

const post = postsData[route.params.slug]
</script>