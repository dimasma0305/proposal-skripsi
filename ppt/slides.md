---
theme: seriph
class: text-center
highlighter: shiki
lineNumbers: false
colorSchema: 'light'
info: |
  ## Proposal Skripsi
  Dimas Maulana
drawings:
  persist: false
transition: slide-left
title: Proposal Skripsi - Dimas Maulana
---


<div class="absolute inset-0 bg-gradient-to-br from-teal-500/5 to-blue-500/5 -z-10 pointer-events-none"></div>

<div class="h-full flex flex-col justify-center items-center">
  <div v-motion
    :initial="{ y: 20, opacity: 0 }"
    :enter="{ y: 0, opacity: 1, transition: { duration: 800 } }"
    class="glass-card p-6 max-w-4xl w-full text-center border-t-4 border-teal-500 shadow-xl -mt-15"
  >
    <!-- Tag -->
    <div class="inline-block px-4 py-1.5 mb-4 text-xs font-bold tracking-[0.2em] text-teal-700 bg-teal-50   rounded-full uppercase shadow-sm">
      Proposal Skripsi
    </div>
    <!-- Title -->
    <div class="text-[48px] font-semibold leading-tight text-gray-800 tracking-tight uppercase">
      PERANCANGAN SISTEM PENDETEKSI <br>
      <span class="text-transparent bg-clip-text bg-gradient-to-r from-teal-600 to-blue-600">KECURANGAN</span> 
      PADA KOMPETISI CYBER SECURITY
    </div>
    <div class="text-[20px] font-semibold text-gray-600  mb-3 leading-relaxed text-center">
      MENGGUNAKAN ALGORITMA <span class="text-teal-600 ">TWO-STAGE SIMILARITY ANALYSIS</span><br>
      DAN <span class="text-blue-600 ">WEIGHTED RISK SCORING</span>
    </div>
    <div class="w-10 h-0.5 bg-gradient-to-r from-teal-500/50 to-blue-500/50 mx-auto mb-3 rounded-full"></div>
    <!-- Author & Inst info -->
    <div class="flex items-center justify-center gap-4 animate-fade-in-up animation-delay-300">
        <img src="/logo.png" class="h-12 w-auto drop-shadow-md hover:scale-105 transition-transform duration-500" alt="Logo PNB" />
        <div class="text-left border-l-2 border-gray-200  pl-4 py-0.5">
            <div class="font-bold text-base text-gray-800  tracking-wide">Dimas Maulana</div>
            <div class="text-xs text-gray-500  font-mono mt-0.5">2215354026</div>
            <div class="text-[0.55rem] font-bold text-teal-600  mt-1 uppercase tracking-widest">D4 Teknologi Rekayasa Perangkat Lunak</div>
        </div>
    </div>
  </div>
</div>

---
layout: default
title: Latar Belakang
---

# Latar Belakang

<div class="grid grid-cols-2 gap-3 mt-2">
  <div v-click class="space-y-2">
    <div class="glass-card p-3">
      <div class="font-bold text-lg text-teal-600 mb-0.5">Evolusi Pendidikan Siber</div>
      <p class="opacity-90 leading-relaxed text-xs">Pergeseran dari pembelajaran teori ke <b>Hands-on</b> melalui kompetisi CTF (Capture The Flag).</p>
    </div>
    <div class="glass-card p-3">
      <div class="font-bold text-lg text-teal-600 mb-0.5">Masalah Integritas</div>
      <p class="opacity-90 leading-relaxed text-xs">Kecurangan (Flag Sharing, Kolusi, Joki) mencederai nilai akademik dan sportivitas.</p>
    </div>
  </div>

  <div v-click class="space-y-2">
    <div class="glass-card p-3 border-l-4 !border-l-red-500">
      <div class="font-bold text-base text-red-600 mb-1">Keterbatasan Saat Ini</div>
      <ul class="list-disc pl-4 opacity-90 space-y-0.5 text-xs">
        <li>Deteksi manual via log (tidak efisien).</li>
        <li>Kurangnya korelasi data otomatis.</li>
        <li>Fitur GZCTF terbatas pada log submission mentah.</li>
      </ul>
    </div>
    <div class="bg-blue-50  p-3 rounded-lg border-l-4 border-blue-500 shadow-md">
      <p class="italic text-xs font-medium">"Tanpa sistem deteksi otomatis, penyelenggara mengandalkan pemeriksaan manual yang rentan human error."</p>
    </div>
  </div>
</div>

---
layout: default
---

# Solusi yang Diusulkan

Membangun **Middleware Deteksi Kecurangan** pada GZCTF dengan pendekatan hibrida:

<div class="grid grid-cols-3 gap-4 mt-4 text-center">
  <div v-click class="glass-card glass-card-hover p-3">
   <div class="text-3xl mb-2">🔍</div>
   <h3 class="font-bold text-sm mb-1 text-teal-600">Sequence Analysis</h3>
   <p class="text-[10px] opacity-80 leading-relaxed">LCS & Jaccard Index untuk mendeteksi kesamaan pola pengerjaan soal.</p>
  </div>

  <div v-click class="glass-card glass-card-hover p-3">
   <div class="text-3xl mb-2">🕸️</div>
   <h3 class="font-bold text-sm mb-1 text-teal-600">Confidence Screening</h3>
   <p class="text-[10px] opacity-80 leading-relaxed">Algoritma CSD untuk memvalidasi kelompok kolusi (Collusion Groups).</p>
  </div>

  <div v-click class="glass-card glass-card-hover p-3">
   <div class="text-3xl mb-2">⚖️</div>
   <h3 class="font-bold text-sm mb-1 text-teal-600">Weighted Risk Scoring</h3>
   <p class="text-[10px] opacity-80 leading-relaxed">Skor risiko terintegrasi dari berbagai anomali (IP, Waktu, Fingerprint).</p>
  </div>
</div>

---

# Rumusan Masalah

<div class="mt-2 grid grid-cols-2 gap-3 max-w-5xl">
  <div v-click class="flex flex-col gap-1 glass-card p-2.5 h-full">
    <div class="flex items-center gap-2">
      <div class="bg-teal-600 text-white rounded-md w-6 h-6 flex items-center justify-center font-bold text-sm shrink-0 shadow-md">1</div>
      <p class="text-xs font-bold text-teal-700">Arsitektur Middleware</p>
    </div>
    <p class="text-[10px] opacity-90 leading-relaxed pl-8">Bagaimana merancang arsitektur middleware yang efektif tanpa mengorbankan performa?</p>
  </div>
  
  <div v-click class="flex flex-col gap-1 glass-card p-2.5 h-full">
    <div class="flex items-center gap-2">
      <div class="bg-teal-600 text-white rounded-md w-6 h-6 flex items-center justify-center font-bold text-sm shrink-0 shadow-md">2</div>
      <p class="text-xs font-bold text-teal-700">Sequence Similarity</p>
    </div>
    <p class="text-[10px] opacity-90 leading-relaxed pl-8">Bagaimana mekanisme implementasi <i>Sequence Similarity Analysis</i> untuk deteksi kolusi?</p>
  </div>

  <div v-click class="flex flex-col gap-1 glass-card p-2.5 h-full">
    <div class="flex items-center gap-2">
      <div class="bg-teal-600 text-white rounded-md w-6 h-6 flex items-center justify-center font-bold text-sm shrink-0 shadow-md">3</div>
      <p class="text-xs font-bold text-teal-700">Risk Scoring</p>
    </div>
    <p class="text-[10px] opacity-90 leading-relaxed pl-8">Bagaimana merumuskan model <i>Weighted Risk Scoring</i> yang optimal?</p>
  </div>

  <div v-click class="flex flex-col gap-1 glass-card p-2.5 h-full">
    <div class="flex items-center gap-2">
      <div class="bg-teal-600 text-white rounded-md w-6 h-6 flex items-center justify-center font-bold text-sm shrink-0 shadow-md">4</div>
      <p class="text-xs font-bold text-teal-700">Akurasi Sistem</p>
    </div>
    <p class="text-[10px] opacity-90 leading-relaxed pl-8">Seberapa besar tingkat akurasi sistem dibandingkan metode manual?</p>
  </div>
</div>

---

# Tujuan Penelitian

<div class="grid grid-cols-2 gap-x-6 gap-y-3 mt-4">
  <div v-click class="glass-card hover:bg-teal-50  p-3 border-l-4 !border-l-teal-500 transition-colors">
 <h3 class="font-bold text-sm text-teal-700  mb-0.5">Modul Middleware</h3>
 <p class="opacity-80 text-xs">Membangun modul deteksi terintegrasi dengan ASP.NET Core GZCTF.</p>
  </div>

  <div v-click class="glass-card hover:bg-teal-50  p-3 border-l-4 !border-l-teal-500 transition-colors">
 <h3 class="font-bold text-sm text-teal-700  mb-0.5">Algoritma Similarity</h3>
 <p class="opacity-80 text-xs">Implementasi LCS + Jaccard dan validasi CSD.</p>
  </div>

  <div v-click class="glass-card hover:bg-teal-50  p-3 border-l-4 !border-l-teal-500 transition-colors">
 <h3 class="font-bold text-sm text-teal-700  mb-0.5">Risk Scoring</h3>
 <p class="opacity-80 text-xs">Sistem pelabelan tingkat kecurigaan otomatis berbasis bobot.</p>
  </div>

  <div v-click class="glass-card hover:bg-teal-50  p-3 border-l-4 !border-l-teal-500 transition-colors">
 <h3 class="font-bold text-sm text-teal-700  mb-0.5">Evaluasi Performa</h3>
 <p class="opacity-80 text-xs">Validasi menggunakan metrik Presisi, Recall, dan F1-Score.</p>
  </div>
</div>

---

# Kerangka Teori

Beberapa konsep kunci yang menjadi landasan penelitian:

<div class="mt-2 grid grid-cols-2 gap-3 text-[10px]">
 <div class="glass-card p-3 hover:border-teal-400 transition-colors">
  <div class="font-bold text-teal-600 mb-0.5 text-xs">GZCTF Framework</div>
  <div class="leading-relaxed opacity-80">Platform CTF open-source berbasis ASP.NET Core dengan arsitektur modular yang mendukung injeksi middleware.</div>
 </div>

 <div class="glass-card p-3 hover:border-teal-400 transition-colors">
  <div class="font-bold text-teal-600 mb-0.5 text-xs">Jaccard Similarity</div>
  <div class="leading-relaxed opacity-80">Mengukur kesamaan himpunan soal yang diselesaikan tanpa memandang urutan.</div>
 </div>

 <div class="glass-card p-3 hover:border-teal-400 transition-colors">
  <div class="font-bold text-teal-600 mb-0.5 text-xs">Longest Common Subsequence (LCS)</div>
  <div class="leading-relaxed opacity-80">Mendeteksi kesamaan urutan kronologis penyelesaian soal untuk indikasi mencontek "step-by-step".</div>
 </div>

 <div class="glass-card p-3 hover:border-teal-400 transition-colors">
  <div class="font-bold text-teal-600 mb-0.5 text-xs">Weighted Risk Scoring</div>
  <div class="leading-relaxed opacity-80">Agregasi berbagai indikator anomali (Shared IP, Fast Solve, dll) menjadi satu skor risiko terukur.</div>
 </div>
</div>

---

# Metodologi Penelitian

Pendekatan **Waterfall** untuk pengembangan sistem terstruktur.

<div class="flex justify-between items-center mt-8 px-4 relative">
  <!-- Line connecting nodes -->
  <div class="absolute top-6 left-0 w-full h-1 bg-gray-200  -z-10"></div>

  <div v-click class="flex flex-col items-center group relative">
    <div class="w-12 h-12 rounded-xl rotate-3 bg-gradient-to-br from-teal-500 to-teal-700 text-white flex items-center justify-center font-bold text-xl mb-2 shadow-lg group-hover:rotate-6 transition-transform">1</div>
    <div class="text-center text-xs font-bold glass-card px-3 py-1.5">Analisis<br>Kebutuhan</div>
  </div>

  <div v-click class="flex flex-col items-center group relative">
    <div class="w-12 h-12 rounded-xl -rotate-2 bg-gradient-to-br from-blue-500 to-blue-700 text-white flex items-center justify-center font-bold text-xl mb-2 shadow-lg group-hover:-rotate-6 transition-transform">2</div>
    <div class="text-center text-xs font-bold glass-card px-3 py-1.5">Perancangan<br>Sistem</div>
  </div>

  <div v-click class="flex flex-col items-center group relative">
    <div class="w-12 h-12 rounded-xl rotate-1 bg-gradient-to-br from-purple-500 to-purple-700 text-white flex items-center justify-center font-bold text-xl mb-2 shadow-lg group-hover:rotate-4 transition-transform">3</div>
    <div class="text-center text-xs font-bold glass-card px-3 py-1.5">Implementasi</div>
  </div>

  <div v-click class="flex flex-col items-center group relative">
    <div class="w-12 h-12 rounded-xl -rotate-3 bg-gradient-to-br from-orange-500 to-orange-700 text-white flex items-center justify-center font-bold text-xl mb-2 shadow-lg group-hover:-rotate-6 transition-transform">4</div>
    <div class="text-center text-xs font-bold glass-card px-3 py-1.5">Pengujian</div>
  </div>

  <div v-click class="flex flex-col items-center group relative">
    <div class="w-12 h-12 rounded-xl rotate-2 bg-gradient-to-br from-green-500 to-green-700 text-white flex items-center justify-center font-bold text-xl mb-2 shadow-lg group-hover:rotate-6 transition-transform">5</div>
    <div class="text-center text-xs font-bold glass-card px-3 py-1.5">Evaluasi</div>
  </div>
</div>

---
layout: center
---

# Arsitektur Sistem

```mermaid
sequenceDiagram
    participant P as Peserta
    participant AM as Auth Middleware
    participant ACM as Anti-Cheat Middleware
    participant L as GZCTF Logic
    participant DB as Database

    P->>AM: POST /submit/flag
    AM->>AM: Validasi Identitas
    AM->>ACM: Forward Request
    Note over ACM: 1. Analisis Risiko Behavior<br>2. Validasi Stolen Flag
    ACM->>DB: Log Kecurangan (Async)
    ACM->>L: Teruskan Request
    L->>DB: Cek Validitas Flag
    L-->>P: Response
```

<p class="text-center text-sm opacity-60 mt-4">Middleware ditempatkan di antara Autentikasi dan Logika Bisnis Utama.</p>

---

# Skenario Pengujian

Validasi sistem melalui berbagai skenario serangan dan anomali.

<div class="overflow-hidden mt-2 rounded-lg shadow-lg border border-gray-200 ">
<table class="premium-table w-full text-xs">
  <thead>
    <tr>
      <th class="py-2 px-3">Kode</th>
      <th class="py-2 px-3">Skenario</th>
      <th class="py-2 px-3">Ekspektasi</th>
    </tr>
  </thead>
  <tbody>
    <tr v-click class="group">
      <td class="font-mono text-teal-600 font-bold group-hover:scale-110 transition-transform origin-left py-2 px-3">TA-01</td>
      <td class="py-2 px-3">Stolen Flag</td>
      <td class="py-2 px-3"><span class="bg-red-100 text-red-700 px-2 py-0.5 rounded text-[10px] font-bold  ">Block Request (403)</span> + Log Critical</td>
    </tr>
    <tr v-click class="group">
      <td class="font-mono text-teal-600 font-bold group-hover:scale-110 transition-transform origin-left py-2 px-3">TA-02</td>
      <td class="py-2 px-3">Flag Sharing (>90% similarity)</td>
      <td class="py-2 px-3">Detect Collusion Group</td>
    </tr>
    <tr v-click class="group">
      <td class="font-mono text-teal-600 font-bold group-hover:scale-110 transition-transform origin-left py-2 px-3">TA-04</td>
      <td class="py-2 px-3">Burst Solve (5 flags/10s)</td>
      <td class="py-2 px-3">Risk Score <span class="text-orange-600 font-bold">+30</span></td>
    </tr>
    <tr v-click class="group">
      <td class="font-mono text-teal-600 font-bold group-hover:scale-110 transition-transform origin-left py-2 px-3">TA-11</td>
      <td class="py-2 px-3">Fast Solve (<2 min)</td>
      <td class="py-2 px-3">Risk Score <span class="text-red-600 font-bold">+50</span></td>
    </tr>
    <tr v-click class="group">
      <td class="font-mono text-teal-600 font-bold group-hover:scale-110 transition-transform origin-left py-2 px-3">Perf</td>
      <td class="py-2 px-3">Load Test (50 concurrent)</td>
      <td class="py-2 px-3">Latency <span class="text-green-600 font-bold">&lt; 300ms</span></td>
    </tr>
  </tbody>
</table>
</div>

---
layout: end
---

# Terima Kasih

<div class="mt-8 text-xl font-medium">Sesi Tanya Jawab</div>

<div class="mt-12 flex justify-center opacity-60">
  <img src="/logo.png" class="w-24 h-auto opacity-50 grayscale" />
</div>
