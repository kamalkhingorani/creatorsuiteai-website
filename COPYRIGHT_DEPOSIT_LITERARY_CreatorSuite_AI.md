# REPRESENTATIONAL SOURCE CODE DEPOSIT — CREATORSUITE AI (LITERARY WORK)

**Author / claimant (edit if needed):** Kamal Kant Hingorani  
**Work:** CreatorSuite AI — public marketing site source (HTML, embedded CSS, client-side script)  
**Repository excerpt generated from:** creatorsuiteai-website (root: index.html, creatorsuite.html, legal.html)  
**Date of this deposit file:** Generated for copyright application packaging.

---

## Important notes (read before filing)

1. **Scope:** This deposit reflects the **static website** published at creatorsuiteai.org (and mirrored on creatorcanvas.org). The **full application** (e.g. React/Next.js on app.creatorsuiteai.org) is a **separate codebase** — if you also register that programme, prepare a **second** excerpt from that repo or add it in consultation with the Copyright Office.

2. **Sensitive content:** No API keys or database connection strings appear in these files. **Third-party vendor names** in legal copy (e.g. payment processors) are **public** business terms. One **infrastructure** label in the Privacy section is generalized to [CLOUD DATABASE PROVIDER] to reduce unnecessary operational specificity. In PART B, the **operational street/area** in the Contact section is replaced with **[REDACTED FOR PRIVACY]** in this deposit only (the live **legal.html** on the site is unchanged). **Public** support emails remain as on the live site.

3. **First / last portions:** Concatenated source order: index.html → creatorsuite.html → legal.html. Total **955** lines (including file banners). **First 500** and **last 500** lines below. Overlap: **45** lines (because total < 1000). This is normal when the work is smaller than 20 printed pages; some guides allow submitting the **entire** programme — you may instead submit this full file as one continuous PDF if the portal allows.

4. **Export to PDF:** Use VS Code / Typora / Word: print to PDF, **monospace font** (e.g. Consolas 9–10pt), A4, margins normal. Keep file **under 10 MB** (this text should be far below).

5. **Footer on each printed page (add in Word/PDF header-footer):**  
   Copyright © 2026 Kamal Kant Hingorani. CreatorSuite AI — source excerpt deposit.

---

## PART A — First 500 lines (concatenated source)

```
/* ===== index.html ===== */
   1  <!DOCTYPE html>
   2  <html lang="en" class="scroll-smooth">
   3  <head>
   4      <meta charset="UTF-8">
   5      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, viewport-fit=cover">
   6      <title>CreatorSuite AI | The Ultimate Toolkit for Creators</title>
   7      <script src="https://cdn.tailwindcss.com"></script>
   8      <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
   9      <style>
  10          * { box-sizing: border-box; }
  11          body { font-family: 'Inter', sans-serif; overflow-x: hidden; word-wrap: break-word; }
  12          .hero-glow {
  13              background: radial-gradient(circle at center, rgba(37, 99, 235, 0.15) 0%, rgba(15, 23, 42, 0) 70%);
  14          }
  15          .glass-panel {
  16              background: rgba(15, 23, 42, 0.6);
  17              backdrop-filter: blur(12px);
  18              border: 1px solid rgba(255, 255, 255, 0.1);
  19          }
  20          /* Mobile: prevent overflow, no overlapping text/borders, keep content in line where possible */
  21          @media (max-width: 1023px) {
  22              .section-pad { padding-left: 1rem; padding-right: 1rem; }
  23              .pricing-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr)); gap: 1rem; align-items: stretch; }
  24              .pricing-card { min-width: 0; flex: 1 1 auto; overflow: hidden; }
  25              .glass-panel { padding: 1rem; min-width: 0; }
  26              .glass-panel h3 { word-break: break-word; }
  27              .glass-panel li { word-break: break-word; overflow-wrap: break-word; min-width: 0; }
  28          }
  29          @media (max-width: 767px) {
  30              .nav-wrap { flex-wrap: wrap; min-height: 4rem; padding: 0.5rem 0.75rem; }
  31              .nav-links { width: 100%; order: 3; display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center; padding-top: 0.5rem; border-top: 1px solid rgba(255,255,255,0.1); }
  32              .hero-title { font-size: 1.75rem; line-height: 2.25rem; }
  33              .footer-links { flex-wrap: wrap; justify-content: center; gap: 0.75rem; }
  34              .pricing-card h3 { font-size: 1rem; }
  35              .pricing-card .text-3xl { font-size: 1.5rem; }
  36              .pricing-card ul li { display: flex; align-items: flex-start; gap: 0.375rem; flex-wrap: nowrap; }
  37              .pricing-card ul li span:first-child { flex-shrink: 0; }
  38              .pricing-card a, .pricing-card button { white-space: normal; word-break: break-word; }
  39          }
  40          @media (max-width: 480px) {
  41              .section-pad { padding-left: 0.75rem; padding-right: 0.75rem; }
  42              .pricing-grid { grid-template-columns: 1fr; gap: 0.75rem; }
  43          }
  44          .feature-card-icon svg { display: block; }
  45          .plan-toggle-btn { padding: 0.5rem 1.25rem; border-radius: 9999px; font-size: 0.875rem; font-weight: 800; text-transform: uppercase; letter-spacing: 0.05em; transition: background .2s, color .2s; }
  46          .plan-toggle-btn-active { background: linear-gradient(to right, #db2777, #f43f5e); color: white; box-shadow: 0 0 20px rgba(236, 72, 153, 0.35); }
  47          .plan-toggle-btn-inactive { color: #94a3b8; }
  48          .plan-toggle-btn-inactive:hover { color: #e2e8f0; }
  49          #pricing-compare .pricing-card-paid, #pricing-compare .pricing-card-free { transition: opacity .35s ease, transform .35s ease, box-shadow .35s ease; }
  50          #pricing-compare:not(.show-pro) .pricing-card-paid { opacity: 0.52; filter: grayscale(0.15); transform: scale(0.98); }
  51          #pricing-compare:not(.show-pro) .pricing-card-free { opacity: 1; box-shadow: 0 0 0 2px rgba(236, 72, 153, 0.55), 0 12px 40px rgba(236, 72, 153, 0.12); transform: scale(1.01); }
  52          #pricing-compare.show-pro .pricing-card-free { opacity: 0.62; }
  53          #pricing-compare.show-pro .pricing-card-paid { opacity: 1; filter: none; transform: scale(1); }
  54          #pricing-compare.show-pro .pricing-card-popular { box-shadow: 0 0 0 2px rgba(168, 85, 247, 0.5); }
  55          @keyframes diff-highlight-pulse {
  56              0%, 100% { box-shadow: 0 0 45px rgba(34,211,238,0.22); border-color: rgba(34, 211, 238, 0.5); }
  57              50% { box-shadow: 0 0 72px rgba(34,211,238,0.45); border-color: rgba(34, 211, 238, 0.85); }
  58          }
  59          .differentiator-pulse { animation: diff-highlight-pulse 3.2s ease-in-out infinite; }
  60      </style>
  61  </head>
  62  <body class="bg-slate-950 text-white antialiased selection:bg-rose-500 selection:text-white min-w-0">
  63  
  64      <nav class="fixed w-full z-50 border-b border-slate-800 bg-slate-950/90 backdrop-blur-md nav-wrap">
  65          <div class="max-w-7xl mx-auto px-4 sm:px-6 h-14 sm:h-20 flex flex-wrap justify-between items-center gap-2">
  66              <a href="index.html" class="flex items-center gap-2 sm:gap-3 group shrink-0">
  67                  <img src="creatorsuite.png" alt="CreatorSuite Logo" width="40" height="40" class="sm:w-[50px] sm:h-auto">
  68                  <div class="font-bold text-base sm:text-xl tracking-tight">CreatorSuite <span class="text-blue-500">AI</span></div>
  69              </a>
  70              <div class="hidden md:flex items-center gap-6 lg:gap-8 text-sm font-medium text-slate-400">
  71                  <a href="#features" class="hover:text-white transition">Features</a>
  72                  <a href="#pricing" class="hover:text-white transition">Pricing</a>
  73                  <a href="https://creatorcanvas.org/" class="hover:text-white transition">← Back to Parent</a>
  74              </div>
  75              <div class="flex items-center gap-2 sm:gap-4 nav-links md:border-0 md:pt-0 md:width-auto md:order-none">
  76                  <a href="#features" class="md:hidden text-slate-400 hover:text-white text-sm">Features</a>
  77                  <a href="#pricing" class="md:hidden text-slate-400 hover:text-white text-sm">Pricing</a>
  78                  <a href="https://creatorcanvas.org/" class="md:hidden text-slate-400 hover:text-white text-sm">Parent</a>
  79                  <a href="https://app.creatorsuiteai.org/login" class="text-sm font-medium text-slate-400 hover:text-white hidden sm:block">Login</a>
  80                  <a href="https://app.creatorsuiteai.org/signup" class="bg-blue-600 hover:bg-blue-500 text-white px-3 py-2 sm:px-5 sm:py-2.5 rounded-lg text-xs sm:text-sm font-bold transition shadow-[0_0_20px_rgba(37,99,235,0.3)] whitespace-nowrap">
  81                      Create Free Account
  82                  </a>
  83              </div>
  84          </div>
  85      </nav>
  86  
  87      <section class="relative pt-24 sm:pt-28 md:pt-32 pb-12 sm:pb-20 overflow-hidden">
  88          <div class="absolute inset-0 hero-glow pointer-events-none"></div>
  89          
  90          <div class="max-w-7xl mx-auto px-4 sm:px-6 section-pad text-center relative z-10">
  91              <div class="inline-block mb-6 sm:mb-8">
  92                  <span class="py-2 sm:py-3 px-4 sm:px-8 rounded-full bg-slate-900 border border-rose-500/50 text-rose-500 font-extrabold text-sm sm:text-xl uppercase tracking-widest shadow-[0_0_15px_rgba(244,63,94,0.3)]">
  93                      The Ultimate Toolkit for Creators
  94                  </span>
  95              </div>
  96              
  97              <h1 class="hero-title text-3xl sm:text-5xl md:text-7xl font-extrabold tracking-tight mb-6 sm:mb-8 leading-tight">
  98                  Create Lots of Content <br>
  99                  <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-cyan-400">In Just 10 Minutes.</span>
 100              </h1>
 101              
 102              <p class="text-base sm:text-lg md:text-xl text-slate-400 mb-4 sm:mb-5 max-w-3xl mx-auto leading-relaxed">
 103                  Compile viral reels from photos, generate multi-lingual scripts, and use deep links to 8 major platforms so you can publish yourself&mdash;CreatorSuite never auto-posts for you. <span class="text-slate-400">The</span> <span class="text-transparent bg-clip-text bg-gradient-to-r from-sky-400 to-cyan-400 font-bold">all-in-one studio</span> <span class="text-white font-semibold">built for Indian &amp; Global growth.</span>
 104              </p>
 105              <p class="max-w-3xl mx-auto mb-6 sm:mb-8 text-slate-200 font-semibold text-sm sm:text-lg tracking-tight px-3 py-2.5 rounded-xl border border-cyan-500/35 bg-gradient-to-r from-slate-900/95 via-cyan-950/45 to-indigo-950/55 ring-1 ring-cyan-500/25 shadow-[0_0_22px_rgba(34,211,238,0.14)]">
 106                  <span class="text-cyan-300 font-bold">24 languages</span> <span class="text-slate-500 font-normal">&middot;</span> <span class="text-indigo-300 font-bold">Location-aware</span> scripts &amp; posts &mdash; <span class="text-fuchsia-400 font-extrabold drop-shadow-[0_0_12px_rgba(232,121,249,0.35)]">your edge</span> <span class="text-slate-500 font-medium">vs</span> <span class="text-slate-300">one-size-fits-all AI</span>
 107              </p>
 108  
 109              <div class="max-w-4xl mx-auto mb-10 sm:mb-12 rounded-2xl border-2 border-cyan-400/50 bg-gradient-to-br from-cyan-950/90 via-slate-900/95 to-indigo-950/90 px-5 sm:px-8 py-6 sm:py-8 shadow-[0_0_45px_rgba(34,211,238,0.22)] ring-1 ring-cyan-500/30 differentiator-pulse">
 110                  <p class="text-center text-[11px] sm:text-xs font-black uppercase tracking-[0.25em] text-cyan-300 mb-2">Differentiator</p>
 111                  <h2 class="text-center text-xl sm:text-3xl font-extrabold mb-3 leading-tight px-1"><span class="text-transparent bg-clip-text bg-gradient-to-r from-fuchsia-400 via-pink-400 to-rose-400 drop-shadow-[0_0_18px_rgba(244,114,182,0.35)]">Multi-lingual</span> <span class="text-white">output &amp;</span> <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-indigo-300">location-aware</span> <span class="text-white">copy</span></h2>
 112                  <p class="text-center text-sm sm:text-base text-slate-200 leading-relaxed mb-4">Generate captions, scripts, blogs &amp; more in <strong class="text-cyan-300">24 languages</strong> (English plus 12 Indian and 11 foreign). Brand DNA blends with <strong class="text-indigo-300">locale, city &amp; tone</strong> so every post reads native to each audience — not generic AI filler.</p>
 113                  <div class="flex flex-wrap justify-center gap-2 sm:gap-3 text-[11px] sm:text-sm font-bold">
 114                      <span class="px-3 py-1.5 rounded-full bg-cyan-500/20 text-cyan-200 border border-cyan-400/40">12 Indian languages (Hindi, Tamil, Telugu, Marathi +)</span>
 115                      <span class="px-3 py-1.5 rounded-full bg-indigo-500/20 text-indigo-200 border border-indigo-400/40">English + 11 foreign (French · Spanish · German · Chinese +)</span>
 116                      <span class="px-3 py-1.5 rounded-full bg-pink-500/15 text-pink-200 border border-pink-500/30">DNA + region tuned</span>
 117                  </div>
 118                  <p class="text-center text-[10px] sm:text-xs text-slate-500 mt-3 max-w-2xl mx-auto leading-relaxed">US / UK / Global under English are <strong class="text-slate-400">locale &amp; tone</strong> (same language, tuned spelling and voice) &mdash; not separate languages. Other rows list distinct languages.</p>
 119              </div>
 120              
 121              <div class="flex flex-col sm:flex-row justify-center gap-4 mb-20">
 122                  <a href="https://app.creatorsuiteai.org/signup" class="bg-blue-600 hover:bg-blue-500 text-white text-lg font-bold px-10 py-4 rounded-xl transition shadow-[0_0_40px_rgba(37,99,235,0.4)] hover:-translate-y-1">
 123                      Start Generating Free ⚡
 124                  </a>
 125              </div>
 126  
 127              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6 max-w-7xl mx-auto mb-12 sm:mb-20">
 128                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500">
 129                      <img src="videomakerv2.png?v=7" alt="Video Studio" class="w-full h-auto" loading="lazy" decoding="async">
 130                      <div class="p-3 bg-slate-950 text-xs text-slate-400 font-bold uppercase tracking-wider">Video Studio</div>
 131                  </div>
 132                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500 md:-translate-y-4 relative z-10">
 133                      <img src="dashboarddna.png?v=7" alt="Main Command Center and Content DNA" class="w-full h-auto" loading="lazy" decoding="async">
 134                      <div class="p-3 bg-slate-950 text-xs text-blue-400 font-bold uppercase tracking-wider">Main Command Center</div>
 135                  </div>
 136                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500">
 137                      <img src="blogwriter.png?v=7" alt="Blog Writer" class="w-full h-auto" loading="lazy" decoding="async">
 138                      <div class="p-3 bg-slate-950 text-xs text-slate-400 font-bold uppercase tracking-wider">Blog Writer</div>
 139                  </div>
 140              </div>
 141              <p class="text-center text-xs sm:text-sm text-slate-400 max-w-3xl mx-auto mb-8 leading-relaxed px-2">These screenshots are from the live app (Video Studio, Dashboard &amp; DNA, Blog Writer). Language coverage: <strong class="text-cyan-300 font-semibold">12 Indian</strong> languages, <strong class="text-slate-300 font-semibold">English</strong>, and <strong class="text-indigo-300 font-semibold">11 foreign</strong> (e.g. French, Spanish, German, Chinese +).</p>
 142              
 143              <div class="flex flex-col items-center">
 144                  <p class="text-slate-500 text-sm mb-6 font-semibold uppercase tracking-wider">Direct Integration With</p>
 145                  <div class="flex flex-wrap justify-center items-center gap-6">
 146                      <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" class="h-10 w-10 hover:scale-110 transition" title="Instagram">
 147                      <img src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg" class="h-10 w-10 hover:scale-110 transition" title="YouTube">
 148                      <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" class="h-10 w-10 hover:scale-110 transition" title="LinkedIn">
 149                      <img src="https://upload.wikimedia.org/wikipedia/commons/5/5a/X_icon_2.svg" class="h-9 w-9 hover:scale-110 transition bg-white rounded-md p-0.5" title="Twitter / X">
 150                      <img src="https://upload.wikimedia.org/wikipedia/commons/b/b8/2021_Facebook_icon.svg" class="h-10 w-10 hover:scale-110 transition" title="Facebook">
 151                      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" class="h-10 w-10 hover:scale-110 transition" title="WhatsApp">
 152                      <img src="https://upload.wikimedia.org/wikipedia/en/c/c4/Snapchat_logo.svg" class="h-10 w-10 hover:scale-110 transition" title="Snapchat">
 153                      <span class="inline-flex h-12 w-12 items-center justify-center hover:scale-110 transition shrink-0" title="TikTok">
 154                          <svg class="h-12 w-12 drop-shadow-[0_0_8px_rgba(37,244,238,0.35)]" viewBox="0 0 24 24" aria-hidden="true" xmlns="http://www.w3.org/2000/svg">
 155                              <defs>
 156                                  <linearGradient id="tiktok-brand-gradient" x1="0%" y1="100%" x2="100%" y2="0%" gradientUnits="objectBoundingBox">
 157                                      <stop offset="0%" stop-color="#25F4EE"/>
 158                                      <stop offset="45%" stop-color="#ffffff"/>
 159                                      <stop offset="100%" stop-color="#FE2C55"/>
 160                                  </linearGradient>
 161                              </defs>
 162                              <path fill="url(#tiktok-brand-gradient)" d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.3-3.65-5.58-.02-.5-.03-1-.01-1.49.14-1.25 1.37-2.28 2.64-2.28.9 0 1.72.46 2.19 1.18.43.66.5 1.52.5 2.29v.75c-.02.08-.02.16-.02.24 0 .32.04.64.14.94.31.96 1.2 1.64 2.22 1.64 1.24 0 2.24-1.02 2.24-2.26 0-1.2-.01-2.4-.01-3.6-.02-3.42-.01-6.84-.02-10.25z"/>
 163                          </svg>
 164                      </span>
 165                  </div>
 166              </div>
 167          </div>
 168      </section>
 169  
 170      <section id="features" class="py-12 sm:py-24 bg-slate-900/30">
 171          <div class="max-w-7xl mx-auto px-4 sm:px-6 section-pad">
 172              <div class="text-center mb-12 sm:mb-16 max-w-3xl mx-auto">
 173                  <h2 class="text-3xl md:text-4xl font-bold mb-3 text-rose-500 drop-shadow-lg">Everything You Need to Go Viral</h2>
 174                  <p class="text-emerald-400 font-semibold text-base sm:text-lg mb-2">One subscription. All the tools.</p>
 175                  <p class="text-slate-400 text-sm sm:text-base">Brand DNA powers every output — from Reels to long-form blogs.</p>
 176                  <p class="text-cyan-300 font-bold text-sm sm:text-base mt-3 leading-snug">Languages &amp; <span class="text-indigo-300">location</span> are first-class: outputs adapt to where your audience lives.</p>
 177              </div>
 178  
 179              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8 lg:gap-10 items-stretch">
 180                  <!-- Content Studio -->
 181                  <div class="glass-panel rounded-2xl border border-slate-700/80 p-8 sm:p-10 shadow-lg shadow-black/20 ring-1 ring-pink-500/20 hover:ring-pink-500/40 transition group relative overflow-hidden">
 182                      <div class="absolute top-0 right-0 bg-gradient-to-r from-blue-600 to-cyan-500 text-white text-[10px] sm:text-xs font-black px-3 sm:px-4 py-1.5 rounded-bl-xl uppercase tracking-widest shadow-lg z-10">Viral Features</div>
 183                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30 mt-1">
 184                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="7" width="20" height="10" rx="2"/><path d="M6 7V5a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v2"/><line x1="12" y1="12" x2="12" y2="12.01"/></svg>
 185                      </div>
 186                      <h3 class="text-xl font-bold mb-3 text-white">Content Studio</h3>
 187                      <p class="text-sm sm:text-base text-slate-200 font-semibold leading-snug mb-5 pl-3 border-l-4 border-pink-500 bg-slate-800/50 py-2.5 pr-2 rounded-r-lg">Free: limited captions, taglines &amp; hashtags. <span class="text-pink-400">Pro unlocks video, calendar, trends &amp; batch.</span></p>
 188                      <ul class="space-y-3 text-sm text-slate-300">
 189                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> Video Maker &amp; Photo Editor</span></li>
 190                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> Video Ideas &amp; Reels (Hook · Body · CTA)</span></li>
 191                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span>Captions, taglines &amp; smart hashtags</span></li>
 192                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> 7-day content calendar</span></li>
 193                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> Carousels · Viral trends · Batch mode</span></li>
 194                      </ul>
 195                  </div>
 196  
 197                  <!-- Strategy & DNA — crown jewels -->
 198                  <div class="glass-panel rounded-2xl border-2 border-purple-500/50 p-8 sm:p-10 shadow-xl shadow-purple-900/25 relative overflow-hidden group">
 199                      <div class="absolute top-0 right-0 bg-gradient-to-r from-pink-600 to-rose-500 text-white text-[10px] sm:text-xs font-black px-3 sm:px-4 py-1.5 rounded-bl-xl uppercase tracking-widest shadow-lg z-10">Most Popular</div>
 200                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30 mt-1">
 201                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.65" stroke-linecap="round" aria-hidden="true"><path d="M5 3c2.5 4.5 2.5 13.5 0 18"/><path d="M19 3c-2.5 4.5-2.5 13.5 0 18"/><line x1="7" y1="7" x2="17" y2="7"/><line x1="8" y1="12" x2="16" y2="12"/><line x1="7" y1="17" x2="17" y2="17"/></svg>
 202                      </div>
 203                      <h3 class="text-xl font-bold mb-3 text-white">Strategy &amp; DNA</h3>
 204                      <p class="text-sm sm:text-base text-slate-200 font-semibold leading-snug mb-5 pl-3 border-l-4 border-purple-500 bg-slate-800/50 py-2.5 pr-2 rounded-r-lg">Brand DNA for everyone. <span class="text-purple-300">Blog Writer, Brand Kit &amp; analysis are Pro.</span></p>
 205                      <ul class="space-y-3 text-sm text-slate-300">
 206                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><strong class="text-white">Brand DNA</strong> — niche, voice, <strong class="text-cyan-300">location</strong> &amp; <strong class="text-indigo-300">language</strong></span></li>
 207                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> Brand analysis &amp; content pillars</span></li>
 208                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> <strong>Blog Writer</strong> — SEO articles, meta &amp; social hooks</span></li>
 209                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span><span class="text-pink-400 font-bold">Pro</span> <strong>Brand Kit</strong> — one-click bios &amp; hashtag packs</span></li>
 210                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span>Custom post starters from your DNA</span></li>
 211                      </ul>
 212                  </div>
 213  
 214                  <!-- Creator League — focused -->
 215                  <div class="glass-panel rounded-2xl border border-emerald-500/30 p-8 sm:p-10 shadow-lg shadow-emerald-900/10 hover:border-emerald-500/50 transition">
 216                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30">
 217                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.65" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M8 21h8"/><path d="M12 17v4"/><path d="M7 4h10v4a5 5 0 0 1-10 0V4z"/><path d="M7 8H5a2 2 0 0 1 0-4h2"/><path d="M17 8h2a2 2 0 0 0 0-4h-2"/></svg>
 218                      </div>
 219                      <h3 class="text-xl font-bold mb-2 text-white">Creator League</h3>
 220                      <p class="text-slate-400 text-sm mb-5">Our exclusive creator community — compete, refer, and win.</p>
 221                      <ul class="space-y-3 text-sm text-slate-300">
 222                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span class="text-emerald-300 font-bold" id="league-prize">Win ₹1,000 + Lifetime Pro</span></li>
 223                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span>Leaderboard &amp; referral rewards</span></li>
 224                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">✅</span><span>Submit ideas &amp; engage with entries</span></li>
 225                      </ul>
 226                      <p class="mt-4 rounded-xl border border-cyan-400/45 bg-gradient-to-r from-cyan-950/75 via-slate-900/85 to-indigo-950/75 px-3.5 py-3.5 text-sm sm:text-base font-semibold leading-snug text-slate-100 shadow-[0_0_24px_rgba(34,211,238,0.2)] ring-1 ring-cyan-500/30"><span class="text-cyan-300">24 languages</span> (English + 12 Indian + 11 foreign) &middot; <span class="text-indigo-300">Location-aware</span> outputs for Indian &amp; global audiences &mdash; core to CreatorSuite, not an afterthought.</p>
 227                      <p class="mt-6 pt-5 border-t border-slate-700/80 text-xs sm:text-sm font-semibold text-slate-200 leading-relaxed">Also in-app: legal document drafts (review with a lawyer), Help Centre with demo &amp; AI chat.</p>
 228                  </div>
 229              </div>
 230          </div>
 231      </section>
 232  
 233      <section id="pricing" class="py-12 sm:py-24">
 234          <div class="max-w-6xl mx-auto px-4 sm:px-6 section-pad">
 235              <div class="text-center mb-8 sm:mb-12">
 236                  <h2 class="text-2xl sm:text-3xl md:text-4xl font-bold mb-4">Transparent Pricing</h2>
 237                  <p class="text-slate-400 text-sm sm:text-base mb-8">Start for free. <span class="text-blue-400 font-bold">Upgrade for faster growth.</span></p>
 238                  <div class="flex flex-col items-center gap-2 mb-8">
 239                      <span class="text-xs font-bold uppercase tracking-widest text-slate-500">Compare plans</span>
 240                      <div class="inline-flex rounded-full bg-slate-900 p-1 border border-slate-700 shadow-inner" role="tablist" aria-label="Free or Pro pricing">
 241                          <button type="button" id="plan-toggle-free" class="plan-toggle-btn plan-toggle-btn-inactive" aria-selected="false">Free</button>
 242                          <button type="button" id="plan-toggle-pro" class="plan-toggle-btn plan-toggle-btn-active" aria-selected="true">Pro plans</button>
 243                      </div>
 244                      <p id="plan-toggle-hint" class="text-xs text-slate-500 max-w-md">Showing paid plans highlighted. Tap <strong class="text-slate-400">Free</strong> to see the starter tier.</p>
 245                  </div>
 246              </div>
 247  
 248              <div id="pricing-compare" class="pricing-grid show-pro grid grid-cols-1 min-[500px]:grid-cols-2 lg:grid-cols-4 gap-4 sm:gap-6 items-stretch">
 249                  <div class="pricing-card pricing-card-free bg-slate-950 border border-slate-800 rounded-xl p-4 sm:p-6 flex flex-col min-w-0">
 250                      <h3 class="text-lg font-bold text-slate-300">Free</h3>
 251                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">₹</span><span id="free-price">0</span></span></div>
 252                      <p class="text-xs text-slate-500 mb-6">Forever free.</p>
 253                      <ul class="space-y-3 mb-8 text-xs text-slate-400 flex-grow">
 254                          <li class="flex gap-2 text-red-400"><span>✕</span> Watermark Forced</li>
 255                          <li class="flex gap-2 text-amber-400"><span>⚠</span> 3 Generations / Day</li>
 256                          <li class="flex gap-2 text-red-400"><span>✕</span> Ads Visible</li>
 257                      </ul>
 258                      <button class="w-full py-2 border border-slate-700 rounded-lg text-sm text-slate-400 cursor-default">Current Plan</button>
 259                      <p class="text-[10px] sm:text-xs text-slate-500 text-center mt-3 pt-3 border-t border-slate-800/80 leading-relaxed">7-day free trial with promo code or referral code</p>
 260                  </div>
 261  
 262                  <div class="pricing-card pricing-card-paid bg-slate-900 border-2 border-blue-600/50 rounded-xl p-4 sm:p-6 flex flex-col min-w-0 hover:border-blue-500 transition shadow-lg shadow-blue-900/10">
 263                      <h3 class="text-lg font-bold text-blue-400">Weekly</h3>
 264                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">₹</span><span id="weekly-price">93</span></span></div>
 265                      <p class="text-xs text-blue-200/90 mb-2 leading-snug font-medium">Perfect for small projects</p>
 266                      <div id="weekly-per-day" class="text-xs text-blue-300 mb-6 font-mono flex items-center gap-1">₹13 / day</div>
 267                      <ul class="space-y-3 mb-8 text-xs text-slate-300 flex-grow">
 268                          <li class="flex gap-2 text-emerald-400"><span>✓</span> Remove Watermark</li>
 269                          <li class="flex gap-2 text-white"><span>🚀</span> <b>10 Gens / Day</b></li>
 270                          <li class="flex gap-2 text-emerald-400"><span>✓</span> No Ads</li>
 271                      </ul>
 272                      <a href="https://app.creatorsuiteai.org/signup?plan=weekly" class="w-full py-2 bg-blue-600 hover:bg-blue-500 text-white text-center rounded-lg text-sm font-bold transition shadow-lg shadow-blue-900/25">Buy Weekly</a>
 273                  </div>
 274  
 275                  <div class="pricing-card pricing-card-paid pricing-card-popular bg-slate-900 border-2 border-purple-600/50 rounded-xl p-4 sm:p-6 relative flex flex-col min-w-0 shadow-lg shadow-purple-900/10">
 276                      <div class="absolute top-0 right-0 bg-purple-600 text-white text-[10px] font-bold px-2 py-1 rounded-bl-lg">POPULAR</div>
 277                      <h3 class="text-lg font-bold text-purple-400">Monthly</h3>
 278                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">₹</span><span id="monthly-price">235</span></span></div>
 279                      <p class="text-xs text-purple-200/90 mb-2 leading-snug font-medium">Flexibility for growing creators</p>
 280                      <div id="monthly-per-day" class="text-xs text-purple-300 mb-6 font-mono flex items-center gap-1">₹8 / day</div>
 281                      <ul class="space-y-3 mb-8 text-xs text-white flex-grow">
 282                          <li class="flex gap-2 text-emerald-400"><span>✓</span> Remove Watermark</li>
 283                          <li class="flex gap-2 text-white"><span>🔥</span> <b>15 Gens / Day</b></li>
 284                          <li class="flex gap-2 text-emerald-400"><span>✓</span> No Ads</li>
 285                      </ul>
 286                      <a href="https://app.creatorsuiteai.org/signup?plan=monthly" class="w-full py-2 bg-purple-600 hover:bg-purple-500 text-center rounded-lg text-sm font-bold text-white transition">Buy Monthly</a>
 287                  </div>
 288  
 289                  <div class="pricing-card pricing-card-paid bg-slate-900 border-2 border-emerald-500 rounded-xl p-4 sm:p-6 flex flex-col relative min-w-0 lg:-translate-y-4 shadow-xl shadow-emerald-900/20">
 290                       <div class="bg-emerald-500 text-slate-900 text-[10px] sm:text-xs font-bold text-center py-1 -mx-4 -mt-4 sm:-mx-6 sm:-mt-6 mb-4 sm:mb-6 rounded-t-lg sm:rounded-t-xl">
 291                          GET 4 MONTHS FREE
 292                      </div>
 293                      <h3 class="text-lg font-bold text-emerald-400">Yearly</h3>
 294                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">₹</span><span id="yearly-price">1,769</span></span></div>
 295                      <p id="yearly-value-line" class="text-xs text-emerald-200/95 mb-1 leading-snug font-medium">Best value: ~₹4.9/day · Save ~37% vs 12× monthly</p>
 296                      <p class="text-[10px] font-bold uppercase tracking-wide text-emerald-100/90 mb-2">Early-adopter rates</p>
 297                      <div id="yearly-per-day" class="text-xs text-emerald-300 mb-6 font-mono flex items-center gap-1">₹5 / day</div>
 298                      <ul class="space-y-3 mb-8 text-xs text-slate-300 flex-grow">
 299                          <li class="flex gap-2 text-emerald-400"><span>✓</span> Remove Watermark</li>
 300                          <li class="flex gap-2 text-white"><span>👑</span> <b>15 Gens / Day</b></li>
 301                          <li class="flex gap-2 text-emerald-400"><span>✓</span> No Ads</li>
 302                      </ul>
 303                      <a href="https://app.creatorsuiteai.org/signup?plan=yearly" class="w-full py-2 bg-emerald-600 hover:bg-emerald-500 text-slate-900 text-center rounded-lg text-sm font-bold transition">Buy Yearly</a>
 304                  </div>
 305              </div>
 306              <p class="text-center text-xs text-slate-600 mt-8">Prices inclusive of taxes. Cancel anytime. <span class="text-slate-500">Email support:</span> <a href="mailto:support@creatorsuiteai.org" class="text-blue-500 hover:text-blue-400">support@creatorsuiteai.org</a></p>
 307          </div>
 308      </section>
 309  
 310      <footer class="py-8 sm:py-10 text-center text-xs sm:text-sm text-slate-500 px-4">
 311      <div class="mb-4">
 312          &copy; <script>document.write(new Date().getFullYear())</script> CreatorSuite AI. 
 313          <span class="text-slate-400">A CreatorCanvas brand.</span>
 314      </div>
 315      
 316      <div class="footer-links flex flex-wrap justify-center gap-3 sm:gap-6">
 317             <a href="legal.html#privacy" class="hover:text-white transition">Privacy Policy</a>
 318             <a href="legal.html#terms" class="hover:text-white transition">Terms of Service</a>
 319             <a href="legal.html#refunds" class="hover:text-white transition">Refund Policy</a>
 320             <a href="legal.html#contact" class="hover:text-white transition">Contact Us</a>
 321      </div>
 322  
 323      <div class="flex flex-wrap justify-center gap-3 sm:gap-6 mt-4 text-xs font-medium">
 324          <a href="mailto:support@creatorsuiteai.org" class="text-blue-500 hover:text-blue-400 flex items-center gap-1 transition">
 325              <span class="opacity-50 text-slate-400">Need Help?</span> support@creatorsuiteai.org
 326          </a>
 327          <a href="mailto:security@creatorsuiteai.org" class="text-emerald-500 hover:text-emerald-400 flex items-center gap-1 transition">
 328              <span class="opacity-50 text-slate-400">Security:</span> security@creatorsuiteai.org
 329          </a>
 330      </div>
 331  </footer>
 332  
 333  <script>
 334  async function setGlobalPricing() {
 335      try {
 336          var cc = '';
 337          try {
 338              const r1 = await fetch('https://ipapi.co/json/?fields=country_code', { cache: 'no-store' });
 339              if (r1.ok) {
 340                  const d1 = await r1.json();
 341                  cc = String(d1.country_code || '').toUpperCase();
 342              }
 343          } catch (e1) { /* try fallback */ }
 344          if (!cc) {
 345              try {
 346                  const r2 = await fetch('https://get.geojs.io/v1/ip/country.json', { cache: 'no-store' });
 347                  if (r2.ok) {
 348                      const d2 = await r2.json();
 349                      cc = String(d2.country || '').toUpperCase();
 350                  }
 351              } catch (e2) { /* keep cc empty */ }
 352          }
 353          /* INR only when geo resolves to India; any other country (or unknown) uses USD for international visitors */
 354          if (cc === 'IN') return;
 355          document.querySelectorAll('.currency-symbol').forEach(function (el) { el.textContent = '$'; });
 356          var fp = document.getElementById('free-price');
 357          if (fp) fp.textContent = '0';
 358          if (document.getElementById('weekly-price')) document.getElementById('weekly-price').textContent = '9';
 359          if (document.getElementById('monthly-price')) document.getElementById('monthly-price').textContent = '25';
 360          if (document.getElementById('yearly-price')) document.getElementById('yearly-price').textContent = '95';
 361          if (document.getElementById('weekly-per-day')) document.getElementById('weekly-per-day').textContent = '$1.29 / day';
 362          if (document.getElementById('monthly-per-day')) document.getElementById('monthly-per-day').textContent = '$0.83 / day';
 363          if (document.getElementById('yearly-per-day')) document.getElementById('yearly-per-day').textContent = '$0.26 / day';
 364          var yvl = document.getElementById('yearly-value-line');
 365          if (yvl) yvl.textContent = 'Best value: ~26¢/day · Save ~68% vs 12× monthly';
 366          var lp = document.getElementById('league-prize');
 367          if (lp) lp.textContent = 'Win $12 + Lifetime Pro';
 368      } catch (e) { console.log('Defaulting to INR', e); }
 369  }
 370  document.addEventListener('DOMContentLoaded', function() {
 371      setGlobalPricing();
 372      var wrap = document.getElementById('pricing-compare');
 373      var btnFree = document.getElementById('plan-toggle-free');
 374      var btnPro = document.getElementById('plan-toggle-pro');
 375      var hint = document.getElementById('plan-toggle-hint');
 376      function setProMode(on) {
 377          if (!wrap) return;
 378          if (on) { wrap.classList.add('show-pro'); } else { wrap.classList.remove('show-pro'); }
 379          if (btnFree && btnPro) {
 380              if (on) {
 381                  btnPro.classList.add('plan-toggle-btn-active'); btnPro.classList.remove('plan-toggle-btn-inactive');
 382                  btnFree.classList.remove('plan-toggle-btn-active'); btnFree.classList.add('plan-toggle-btn-inactive');
 383                  btnPro.setAttribute('aria-selected', 'true'); btnFree.setAttribute('aria-selected', 'false');
 384              } else {
 385                  btnFree.classList.add('plan-toggle-btn-active'); btnFree.classList.remove('plan-toggle-btn-inactive');
 386                  btnPro.classList.remove('plan-toggle-btn-active'); btnPro.classList.add('plan-toggle-btn-inactive');
 387                  btnFree.setAttribute('aria-selected', 'true'); btnPro.setAttribute('aria-selected', 'false');
 388              }
 389          }
 390          if (hint) hint.innerHTML = on
 391              ? 'Paid plans highlighted. Tap <strong class="text-slate-400">Free</strong> to compare the starter tier.'
 392              : 'Free tier highlighted. Tap <strong class="text-slate-400">Pro plans</strong> to see Weekly, Monthly &amp; Yearly.';
 393      }
 394      if (btnFree) btnFree.addEventListener('click', function() { setProMode(false); });
 395      if (btnPro) btnPro.addEventListener('click', function() { setProMode(true); });
 396  });
 397  </script>
 398  </body>
 399  </html>

/* ===== creatorsuite.html ===== */
   1  <!DOCTYPE html>
   2  <html lang="en" class="scroll-smooth">
   3  <head>
   4      <meta charset="UTF-8">
   5      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, viewport-fit=cover">
   6      <title>CreatorSuite AI | The Ultimate Toolkit for Creators</title>
   7      <script src="https://cdn.tailwindcss.com"></script>
   8      <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
   9      <style>
  10          * { box-sizing: border-box; }
  11          body { font-family: 'Inter', sans-serif; overflow-x: hidden; word-wrap: break-word; }
  12          .hero-glow {
  13              background: radial-gradient(circle at center, rgba(37, 99, 235, 0.15) 0%, rgba(15, 23, 42, 0) 70%);
  14          }
  15          .glass-panel {
  16              background: rgba(15, 23, 42, 0.6);
  17              backdrop-filter: blur(12px);
  18              border: 1px solid rgba(255, 255, 255, 0.1);
  19          }
  20          /* Mobile: prevent overflow, no overlapping text/borders, keep content in line where possible */
  21          @media (max-width: 1023px) {
  22              .section-pad { padding-left: 1rem; padding-right: 1rem; }
  23              .pricing-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr)); gap: 1rem; align-items: stretch; }
  24              .pricing-card { min-width: 0; flex: 1 1 auto; overflow: hidden; }
  25              .glass-panel { padding: 1rem; min-width: 0; }
  26              .glass-panel h3 { word-break: break-word; }
  27              .glass-panel li { word-break: break-word; overflow-wrap: break-word; min-width: 0; }
  28          }
  29          @media (max-width: 767px) {
  30              .nav-wrap { flex-wrap: wrap; min-height: 4rem; padding: 0.5rem 0.75rem; }
  31              .nav-links { width: 100%; order: 3; display: flex; flex-wrap: wrap; gap: 0.5rem; justify-content: center; padding-top: 0.5rem; border-top: 1px solid rgba(255,255,255,0.1); }
  32              .hero-title { font-size: 1.75rem; line-height: 2.25rem; }
  33              .footer-links { flex-wrap: wrap; justify-content: center; gap: 0.75rem; }
  34              .pricing-card h3 { font-size: 1rem; }
  35              .pricing-card .text-3xl { font-size: 1.5rem; }
  36              .pricing-card ul li { display: flex; align-items: flex-start; gap: 0.375rem; flex-wrap: nowrap; }
  37              .pricing-card ul li span:first-child { flex-shrink: 0; }
  38              .pricing-card a, .pricing-card button { white-space: normal; word-break: break-word; }
  39          }
  40          @media (max-width: 480px) {
  41              .section-pad { padding-left: 0.75rem; padding-right: 0.75rem; }
  42              .pricing-grid { grid-template-columns: 1fr; gap: 0.75rem; }
  43          }
  44          .feature-card-icon svg { display: block; }
  45          .plan-toggle-btn { padding: 0.5rem 1.25rem; border-radius: 9999px; font-size: 0.875rem; font-weight: 800; text-transform: uppercase; letter-spacing: 0.05em; transition: background .2s, color .2s; }
  46          .plan-toggle-btn-active { background: linear-gradient(to right, #db2777, #f43f5e); color: white; box-shadow: 0 0 20px rgba(236, 72, 153, 0.35); }
  47          .plan-toggle-btn-inactive { color: #94a3b8; }
  48          .plan-toggle-btn-inactive:hover { color: #e2e8f0; }
  49          #pricing-compare .pricing-card-paid, #pricing-compare .pricing-card-free { transition: opacity .35s ease, transform .35s ease, box-shadow .35s ease; }
  50          #pricing-compare:not(.show-pro) .pricing-card-paid { opacity: 0.52; filter: grayscale(0.15); transform: scale(0.98); }
  51          #pricing-compare:not(.show-pro) .pricing-card-free { opacity: 1; box-shadow: 0 0 0 2px rgba(236, 72, 153, 0.55), 0 12px 40px rgba(236, 72, 153, 0.12); transform: scale(1.01); }
  52          #pricing-compare.show-pro .pricing-card-free { opacity: 0.62; }
  53          #pricing-compare.show-pro .pricing-card-paid { opacity: 1; filter: none; transform: scale(1); }
  54          #pricing-compare.show-pro .pricing-card-popular { box-shadow: 0 0 0 2px rgba(168, 85, 247, 0.5); }
  55          @keyframes diff-highlight-pulse {
  56              0%, 100% { box-shadow: 0 0 45px rgba(34,211,238,0.22); border-color: rgba(34, 211, 238, 0.5); }
  57              50% { box-shadow: 0 0 72px rgba(34,211,238,0.45); border-color: rgba(34, 211, 238, 0.85); }
  58          }
  59          .differentiator-pulse { animation: diff-highlight-pulse 3.2s ease-in-out infinite; }
  60      </style>
  61  </head>
  62  <body class="bg-slate-950 text-white antialiased selection:bg-rose-500 selection:text-white min-w-0">
  63  
  64      <nav class="fixed w-full z-50 border-b border-slate-800 bg-slate-950/90 backdrop-blur-md nav-wrap">
  65          <div class="max-w-7xl mx-auto px-4 sm:px-6 h-14 sm:h-20 flex flex-wrap justify-between items-center gap-2">
  66              <a href="index.html" class="flex items-center gap-2 sm:gap-3 group shrink-0">
  67                  <img src="creatorsuite.png" alt="CreatorSuite Logo" width="40" height="40" class="sm:w-[50px] sm:h-auto">
  68                  <div class="font-bold text-base sm:text-xl tracking-tight">CreatorSuite <span class="text-blue-500">AI</span></div>
  69              </a>
  70              <div class="hidden md:flex items-center gap-6 lg:gap-8 text-sm font-medium text-slate-400">
  71                  <a href="#features" class="hover:text-white transition">Features</a>
  72                  <a href="#pricing" class="hover:text-white transition">Pricing</a>
  73                  <a href="https://creatorcanvas.org/" class="hover:text-white transition">&larr; Back to Parent</a>
  74              </div>
  75              <div class="flex items-center gap-2 sm:gap-4 nav-links md:border-0 md:pt-0 md:width-auto md:order-none">
  76                  <a href="#features" class="md:hidden text-slate-400 hover:text-white text-sm">Features</a>
  77                  <a href="#pricing" class="md:hidden text-slate-400 hover:text-white text-sm">Pricing</a>
  78                  <a href="https://creatorcanvas.org/" class="md:hidden text-slate-400 hover:text-white text-sm">Parent</a>
  79                  <a href="https://app.creatorsuiteai.org/login" class="text-sm font-medium text-slate-400 hover:text-white hidden sm:block">Login</a>
  80                  <a href="https://app.creatorsuiteai.org/signup" class="bg-blue-600 hover:bg-blue-500 text-white px-3 py-2 sm:px-5 sm:py-2.5 rounded-lg text-xs sm:text-sm font-bold transition shadow-[0_0_20px_rgba(37,99,235,0.3)] whitespace-nowrap">
  81                      Create Free Account
  82                  </a>
  83              </div>
  84          </div>
  85      </nav>
  86  
  87      <section class="relative pt-24 sm:pt-28 md:pt-32 pb-12 sm:pb-20 overflow-hidden">
  88          <div class="absolute inset-0 hero-glow pointer-events-none"></div>
  89          
  90          <div class="max-w-7xl mx-auto px-4 sm:px-6 section-pad text-center relative z-10">
  91              <div class="inline-block mb-6 sm:mb-8">
  92                  <span class="py-2 sm:py-3 px-4 sm:px-8 rounded-full bg-slate-900 border border-rose-500/50 text-rose-500 font-extrabold text-sm sm:text-xl uppercase tracking-widest shadow-[0_0_15px_rgba(244,63,94,0.3)]">
  93                      The Ultimate Toolkit for Creators
  94                  </span>
  95              </div>
  96              
  97              <h1 class="hero-title text-3xl sm:text-5xl md:text-7xl font-extrabold tracking-tight mb-6 sm:mb-8 leading-tight">
```

---

## PART B — Last 500 lines (concatenated source)

```
  53          #pricing-compare.show-pro .pricing-card-paid { opacity: 1; filter: none; transform: scale(1); }
  54          #pricing-compare.show-pro .pricing-card-popular { box-shadow: 0 0 0 2px rgba(168, 85, 247, 0.5); }
  55          @keyframes diff-highlight-pulse {
  56              0%, 100% { box-shadow: 0 0 45px rgba(34,211,238,0.22); border-color: rgba(34, 211, 238, 0.5); }
  57              50% { box-shadow: 0 0 72px rgba(34,211,238,0.45); border-color: rgba(34, 211, 238, 0.85); }
  58          }
  59          .differentiator-pulse { animation: diff-highlight-pulse 3.2s ease-in-out infinite; }
  60      </style>
  61  </head>
  62  <body class="bg-slate-950 text-white antialiased selection:bg-rose-500 selection:text-white min-w-0">
  63  
  64      <nav class="fixed w-full z-50 border-b border-slate-800 bg-slate-950/90 backdrop-blur-md nav-wrap">
  65          <div class="max-w-7xl mx-auto px-4 sm:px-6 h-14 sm:h-20 flex flex-wrap justify-between items-center gap-2">
  66              <a href="index.html" class="flex items-center gap-2 sm:gap-3 group shrink-0">
  67                  <img src="creatorsuite.png" alt="CreatorSuite Logo" width="40" height="40" class="sm:w-[50px] sm:h-auto">
  68                  <div class="font-bold text-base sm:text-xl tracking-tight">CreatorSuite <span class="text-blue-500">AI</span></div>
  69              </a>
  70              <div class="hidden md:flex items-center gap-6 lg:gap-8 text-sm font-medium text-slate-400">
  71                  <a href="#features" class="hover:text-white transition">Features</a>
  72                  <a href="#pricing" class="hover:text-white transition">Pricing</a>
  73                  <a href="https://creatorcanvas.org/" class="hover:text-white transition">&larr; Back to Parent</a>
  74              </div>
  75              <div class="flex items-center gap-2 sm:gap-4 nav-links md:border-0 md:pt-0 md:width-auto md:order-none">
  76                  <a href="#features" class="md:hidden text-slate-400 hover:text-white text-sm">Features</a>
  77                  <a href="#pricing" class="md:hidden text-slate-400 hover:text-white text-sm">Pricing</a>
  78                  <a href="https://creatorcanvas.org/" class="md:hidden text-slate-400 hover:text-white text-sm">Parent</a>
  79                  <a href="https://app.creatorsuiteai.org/login" class="text-sm font-medium text-slate-400 hover:text-white hidden sm:block">Login</a>
  80                  <a href="https://app.creatorsuiteai.org/signup" class="bg-blue-600 hover:bg-blue-500 text-white px-3 py-2 sm:px-5 sm:py-2.5 rounded-lg text-xs sm:text-sm font-bold transition shadow-[0_0_20px_rgba(37,99,235,0.3)] whitespace-nowrap">
  81                      Create Free Account
  82                  </a>
  83              </div>
  84          </div>
  85      </nav>
  86  
  87      <section class="relative pt-24 sm:pt-28 md:pt-32 pb-12 sm:pb-20 overflow-hidden">
  88          <div class="absolute inset-0 hero-glow pointer-events-none"></div>
  89          
  90          <div class="max-w-7xl mx-auto px-4 sm:px-6 section-pad text-center relative z-10">
  91              <div class="inline-block mb-6 sm:mb-8">
  92                  <span class="py-2 sm:py-3 px-4 sm:px-8 rounded-full bg-slate-900 border border-rose-500/50 text-rose-500 font-extrabold text-sm sm:text-xl uppercase tracking-widest shadow-[0_0_15px_rgba(244,63,94,0.3)]">
  93                      The Ultimate Toolkit for Creators
  94                  </span>
  95              </div>
  96              
  97              <h1 class="hero-title text-3xl sm:text-5xl md:text-7xl font-extrabold tracking-tight mb-6 sm:mb-8 leading-tight">
  98                  Create Lots of Content <br>
  99                  <span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-cyan-400">In Just 10 Minutes.</span>
 100              </h1>
 101              
 102              <p class="text-base sm:text-lg md:text-xl text-slate-400 mb-4 sm:mb-5 max-w-3xl mx-auto leading-relaxed">
 103                  Compile viral reels from photos, generate multi-lingual scripts, and use deep links to 8 major platforms so you can publish yourself&mdash;CreatorSuite never auto-posts for you. <span class="text-slate-400">The</span> <span class="text-transparent bg-clip-text bg-gradient-to-r from-sky-400 to-cyan-400 font-bold">all-in-one studio</span> <span class="text-white font-semibold">built for Indian &amp; Global growth.</span>
 104              </p>
 105              <p class="max-w-3xl mx-auto mb-6 sm:mb-8 text-slate-200 font-semibold text-sm sm:text-lg tracking-tight px-3 py-2.5 rounded-xl border border-cyan-500/35 bg-gradient-to-r from-slate-900/95 via-cyan-950/45 to-indigo-950/55 ring-1 ring-cyan-500/25 shadow-[0_0_22px_rgba(34,211,238,0.14)]">
 106                  <span class="text-cyan-300 font-bold">24 languages</span> <span class="text-slate-500 font-normal">&middot;</span> <span class="text-indigo-300 font-bold">Location-aware</span> scripts &amp; posts &mdash; <span class="text-fuchsia-400 font-extrabold drop-shadow-[0_0_12px_rgba(232,121,249,0.35)]">your edge</span> <span class="text-slate-500 font-medium">vs</span> <span class="text-slate-300">one-size-fits-all AI</span>
 107              </p>
 108  
 109              <div class="max-w-4xl mx-auto mb-10 sm:mb-12 rounded-2xl border-2 border-cyan-400/50 bg-gradient-to-br from-cyan-950/90 via-slate-900/95 to-indigo-950/90 px-5 sm:px-8 py-6 sm:py-8 shadow-[0_0_45px_rgba(34,211,238,0.22)] ring-1 ring-cyan-500/30 differentiator-pulse">
 110                  <p class="text-center text-[11px] sm:text-xs font-black uppercase tracking-[0.25em] text-cyan-300 mb-2">Differentiator</p>
 111                  <h2 class="text-center text-xl sm:text-3xl font-extrabold mb-3 leading-tight px-1"><span class="text-transparent bg-clip-text bg-gradient-to-r from-fuchsia-400 via-pink-400 to-rose-400 drop-shadow-[0_0_18px_rgba(244,114,182,0.35)]">Multi-lingual</span> <span class="text-white">output &amp;</span> <span class="text-transparent bg-clip-text bg-gradient-to-r from-cyan-300 to-indigo-300">location-aware</span> <span class="text-white">copy</span></h2>
 112                  <p class="text-center text-sm sm:text-base text-slate-200 leading-relaxed mb-4">Generate captions, scripts, blogs &amp; more in <strong class="text-cyan-300">24 languages</strong> (English plus 12 Indian and 11 foreign). Brand DNA blends with <strong class="text-indigo-300">locale, city &amp; tone</strong> so every post reads native to each audience &mdash; not generic AI filler.</p>
 113                  <div class="flex flex-wrap justify-center gap-2 sm:gap-3 text-[11px] sm:text-sm font-bold">
 114                      <span class="px-3 py-1.5 rounded-full bg-cyan-500/20 text-cyan-200 border border-cyan-400/40">12 Indian languages (Hindi, Tamil, Telugu, Marathi +)</span>
 115                      <span class="px-3 py-1.5 rounded-full bg-indigo-500/20 text-indigo-200 border border-indigo-400/40">English + 11 foreign (French &middot; Spanish &middot; German &middot; Chinese +)</span>
 116                      <span class="px-3 py-1.5 rounded-full bg-pink-500/15 text-pink-200 border border-pink-500/30">DNA + region tuned</span>
 117                  </div>
 118                  <p class="text-center text-[10px] sm:text-xs text-slate-500 mt-3 max-w-2xl mx-auto leading-relaxed">US / UK / Global under English are <strong class="text-slate-400">locale &amp; tone</strong> (same language, tuned spelling and voice) &mdash; not separate languages. Other rows list distinct languages.</p>
 119              </div>
 120              
 121              <div class="flex flex-col sm:flex-row justify-center gap-4 mb-20">
 122                  <a href="https://app.creatorsuiteai.org/signup" class="bg-blue-600 hover:bg-blue-500 text-white text-lg font-bold px-10 py-4 rounded-xl transition shadow-[0_0_40px_rgba(37,99,235,0.4)] hover:-translate-y-1">
 123                      Start Generating Free &#9889;
 124                  </a>
 125              </div>
 126  
 127              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6 max-w-7xl mx-auto mb-12 sm:mb-20">
 128                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500">
 129                      <img src="videomakerv2.png?v=7" alt="Video Studio" class="w-full h-auto" loading="lazy" decoding="async">
 130                      <div class="p-3 bg-slate-950 text-xs text-slate-400 font-bold uppercase tracking-wider">Video Studio</div>
 131                  </div>
 132                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500 md:-translate-y-4 relative z-10">
 133                      <img src="dashboarddna.png?v=7" alt="Main Command Center and Content DNA" class="w-full h-auto" loading="lazy" decoding="async">
 134                      <div class="p-3 bg-slate-950 text-xs text-blue-400 font-bold uppercase tracking-wider">Main Command Center</div>
 135                  </div>
 136                  <div class="bg-slate-900 rounded-xl border border-slate-800 overflow-hidden shadow-2xl hover:scale-105 transition duration-500">
 137                      <img src="blogwriter.png?v=7" alt="Blog Writer" class="w-full h-auto" loading="lazy" decoding="async">
 138                      <div class="p-3 bg-slate-950 text-xs text-slate-400 font-bold uppercase tracking-wider">Blog Writer</div>
 139                  </div>
 140              </div>
 141              <p class="text-center text-xs sm:text-sm text-slate-400 max-w-3xl mx-auto mb-8 leading-relaxed px-2">These screenshots are from the live app (Video Studio, Dashboard &amp; DNA, Blog Writer). Language coverage: <strong class="text-cyan-300 font-semibold">12 Indian</strong> languages, <strong class="text-slate-300 font-semibold">English</strong>, and <strong class="text-indigo-300 font-semibold">11 foreign</strong> (e.g. French, Spanish, German, Chinese +).</p>
 142              
 143              <div class="flex flex-col items-center">
 144                  <p class="text-slate-500 text-sm mb-6 font-semibold uppercase tracking-wider">Direct Integration With</p>
 145                  <div class="flex flex-wrap justify-center items-center gap-6">
 146                      <img src="https://upload.wikimedia.org/wikipedia/commons/e/e7/Instagram_logo_2016.svg" class="h-10 w-10 hover:scale-110 transition" title="Instagram">
 147                      <img src="https://upload.wikimedia.org/wikipedia/commons/0/09/YouTube_full-color_icon_%282017%29.svg" class="h-10 w-10 hover:scale-110 transition" title="YouTube">
 148                      <img src="https://upload.wikimedia.org/wikipedia/commons/c/ca/LinkedIn_logo_initials.png" class="h-10 w-10 hover:scale-110 transition" title="LinkedIn">
 149                      <img src="https://upload.wikimedia.org/wikipedia/commons/5/5a/X_icon_2.svg" class="h-9 w-9 hover:scale-110 transition bg-white rounded-md p-0.5" title="Twitter / X">
 150                      <img src="https://upload.wikimedia.org/wikipedia/commons/b/b8/2021_Facebook_icon.svg" class="h-10 w-10 hover:scale-110 transition" title="Facebook">
 151                      <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" class="h-10 w-10 hover:scale-110 transition" title="WhatsApp">
 152                      <img src="https://upload.wikimedia.org/wikipedia/en/c/c4/Snapchat_logo.svg" class="h-10 w-10 hover:scale-110 transition" title="Snapchat">
 153                      <span class="inline-flex h-12 w-12 items-center justify-center hover:scale-110 transition shrink-0" title="TikTok">
 154                          <svg class="h-12 w-12 drop-shadow-[0_0_8px_rgba(37,244,238,0.35)]" viewBox="0 0 24 24" aria-hidden="true" xmlns="http://www.w3.org/2000/svg">
 155                              <defs>
 156                                  <linearGradient id="tiktok-brand-gradient-cs" x1="0%" y1="100%" x2="100%" y2="0%" gradientUnits="objectBoundingBox">
 157                                      <stop offset="0%" stop-color="#25F4EE"/>
 158                                      <stop offset="45%" stop-color="#ffffff"/>
 159                                      <stop offset="100%" stop-color="#FE2C55"/>
 160                                  </linearGradient>
 161                              </defs>
 162                              <path fill="url(#tiktok-brand-gradient-cs)" d="M12.525.02c1.31-.02 2.61-.01 3.91-.02.08 1.53.63 3.09 1.75 4.17 1.12 1.11 2.7 1.62 4.24 1.79v4.03c-1.44-.05-2.89-.35-4.2-.97-.57-.26-1.1-.59-1.62-.93-.01 2.92.01 5.84-.02 8.75-.08 1.4-.54 2.79-1.35 3.94-1.31 1.92-3.58 3.17-5.91 3.21-1.43.08-2.86-.31-4.08-1.03-2.02-1.19-3.44-3.3-3.65-5.58-.02-.5-.03-1-.01-1.49.14-1.25 1.37-2.28 2.64-2.28.9 0 1.72.46 2.19 1.18.43.66.5 1.52.5 2.29v.75c-.02.08-.02.16-.02.24 0 .32.04.64.14.94.31.96 1.2 1.64 2.22 1.64 1.24 0 2.24-1.02 2.24-2.26 0-1.2-.01-2.4-.01-3.6-.02-3.42-.01-6.84-.02-10.25z"/>
 163                          </svg>
 164                      </span>
 165                  </div>
 166              </div>
 167          </div>
 168      </section>
 169  
 170      <section id="features" class="py-12 sm:py-24 bg-slate-900/30">
 171          <div class="max-w-7xl mx-auto px-4 sm:px-6 section-pad">
 172              <div class="text-center mb-12 sm:mb-16 max-w-3xl mx-auto">
 173                  <h2 class="text-3xl md:text-4xl font-bold mb-3 text-rose-500 drop-shadow-lg">Everything You Need to Go Viral</h2>
 174                  <p class="text-emerald-400 font-semibold text-base sm:text-lg mb-2">One subscription. All the tools.</p>
 175                  <p class="text-slate-400 text-sm sm:text-base">Brand DNA powers every output &mdash; from Reels to long-form blogs.</p>
 176                  <p class="text-cyan-300 font-bold text-sm sm:text-base mt-3 leading-snug">Languages &amp; <span class="text-indigo-300">location</span> are first-class: outputs adapt to where your audience lives.</p>
 177              </div>
 178  
 179              <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 sm:gap-8 lg:gap-10 items-stretch">
 180                  <!-- Content Studio -->
 181                  <div class="glass-panel rounded-2xl border border-slate-700/80 p-8 sm:p-10 shadow-lg shadow-black/20 ring-1 ring-pink-500/20 hover:ring-pink-500/40 transition group relative overflow-hidden">
 182                      <div class="absolute top-0 right-0 bg-gradient-to-r from-blue-600 to-cyan-500 text-white text-[10px] sm:text-xs font-black px-3 sm:px-4 py-1.5 rounded-bl-xl uppercase tracking-widest shadow-lg z-10">Viral Features</div>
 183                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30 mt-1">
 184                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.75" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><rect x="2" y="7" width="20" height="10" rx="2"/><path d="M6 7V5a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v2"/><line x1="12" y1="12" x2="12" y2="12.01"/></svg>
 185                      </div>
 186                      <h3 class="text-xl font-bold mb-3 text-white">Content Studio</h3>
 187                      <p class="text-sm sm:text-base text-slate-200 font-semibold leading-snug mb-5 pl-3 border-l-4 border-pink-500 bg-slate-800/50 py-2.5 pr-2 rounded-r-lg">Free: limited captions, taglines &amp; hashtags. <span class="text-pink-400">Pro unlocks video, calendar, trends &amp; batch.</span></p>
 188                      <ul class="space-y-3 text-sm text-slate-300">
 189                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> Video Maker &amp; Photo Editor</span></li>
 190                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> Video Ideas &amp; Reels (Hook &middot; Body &middot; CTA)</span></li>
 191                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span>Captions, taglines &amp; smart hashtags</span></li>
 192                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> 7-day content calendar</span></li>
 193                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> Carousels &middot; Viral trends &middot; Batch mode</span></li>
 194                      </ul>
 195                  </div>
 196  
 197                  <!-- Strategy & DNA - crown jewels -->
 198                  <div class="glass-panel rounded-2xl border-2 border-purple-500/50 p-8 sm:p-10 shadow-xl shadow-purple-900/25 relative overflow-hidden group">
 199                      <div class="absolute top-0 right-0 bg-gradient-to-r from-pink-600 to-rose-500 text-white text-[10px] sm:text-xs font-black px-3 sm:px-4 py-1.5 rounded-bl-xl uppercase tracking-widest shadow-lg z-10">Most Popular</div>
 200                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30 mt-1">
 201                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.65" stroke-linecap="round" aria-hidden="true"><path d="M5 3c2.5 4.5 2.5 13.5 0 18"/><path d="M19 3c-2.5 4.5-2.5 13.5 0 18"/><line x1="7" y1="7" x2="17" y2="7"/><line x1="8" y1="12" x2="16" y2="12"/><line x1="7" y1="17" x2="17" y2="17"/></svg>
 202                      </div>
 203                      <h3 class="text-xl font-bold mb-3 text-white">Strategy &amp; DNA</h3>
 204                      <p class="text-sm sm:text-base text-slate-200 font-semibold leading-snug mb-5 pl-3 border-l-4 border-purple-500 bg-slate-800/50 py-2.5 pr-2 rounded-r-lg">Brand DNA for everyone. <span class="text-purple-300">Blog Writer, Brand Kit &amp; analysis are Pro.</span></p>
 205                      <ul class="space-y-3 text-sm text-slate-300">
 206                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><strong class="text-white">Brand DNA</strong> &mdash; niche, voice, <strong class="text-cyan-300">location</strong> &amp; <strong class="text-indigo-300">language</strong></span></li>
 207                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> Brand analysis &amp; content pillars</span></li>
 208                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> <strong>Blog Writer</strong> &mdash; SEO articles, meta &amp; social hooks</span></li>
 209                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span><span class="text-pink-400 font-bold">Pro</span> <strong>Brand Kit</strong> &mdash; one-click bios &amp; hashtag packs</span></li>
 210                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span>Custom post starters from your DNA</span></li>
 211                      </ul>
 212                  </div>
 213  
 214                  <!-- Creator League - focused -->
 215                  <div class="glass-panel rounded-2xl border border-emerald-500/30 p-8 sm:p-10 shadow-lg shadow-emerald-900/10 hover:border-emerald-500/50 transition">
 216                      <div class="feature-card-icon h-12 w-12 rounded-xl bg-pink-500/15 flex items-center justify-center mb-6 border border-pink-500/30">
 217                          <svg class="w-7 h-7 text-pink-500" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.65" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M8 21h8"/><path d="M12 17v4"/><path d="M7 4h10v4a5 5 0 0 1-10 0V4z"/><path d="M7 8H5a2 2 0 0 1 0-4h2"/><path d="M17 8h2a2 2 0 0 0 0-4h-2"/></svg>
 218                      </div>
 219                      <h3 class="text-xl font-bold mb-2 text-white">Creator League</h3>
 220                      <p class="text-slate-400 text-sm mb-5">Our exclusive creator community &mdash; compete, refer, and win.</p>
 221                      <ul class="space-y-3 text-sm text-slate-300">
 222                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span class="text-emerald-300 font-bold" id="league-prize">Win &#8377;1,000 + Lifetime Pro</span></li>
 223                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span>Leaderboard &amp; referral rewards</span></li>
 224                          <li class="flex gap-2.5 items-start"><span class="text-emerald-400 shrink-0 mt-0.5" aria-hidden="true">&#9989;</span><span>Submit ideas &amp; engage with entries</span></li>
 225                      </ul>
 226                      <p class="mt-4 rounded-xl border border-cyan-400/45 bg-gradient-to-r from-cyan-950/75 via-slate-900/85 to-indigo-950/75 px-3.5 py-3.5 text-sm sm:text-base font-semibold leading-snug text-slate-100 shadow-[0_0_24px_rgba(34,211,238,0.2)] ring-1 ring-cyan-500/30"><span class="text-cyan-300">24 languages</span> (English + 12 Indian + 11 foreign) &middot; <span class="text-indigo-300">Location-aware</span> outputs for Indian &amp; global audiences &mdash; core to CreatorSuite, not an afterthought.</p>
 227                      <p class="mt-6 pt-5 border-t border-slate-700/80 text-xs sm:text-sm font-semibold text-slate-200 leading-relaxed">Also in-app: legal document drafts (review with a lawyer), Help Centre with demo &amp; AI chat.</p>
 228                  </div>
 229              </div>
 230          </div>
 231      </section>
 232  
 233      <section id="pricing" class="py-12 sm:py-24">
 234          <div class="max-w-6xl mx-auto px-4 sm:px-6 section-pad">
 235              <div class="text-center mb-8 sm:mb-12">
 236                  <h2 class="text-2xl sm:text-3xl md:text-4xl font-bold mb-4">Transparent Pricing</h2>
 237                  <p class="text-slate-400 text-sm sm:text-base mb-8">Start for free. <span class="text-blue-400 font-bold">Upgrade for faster growth.</span></p>
 238                  <div class="flex flex-col items-center gap-2 mb-8">
 239                      <span class="text-xs font-bold uppercase tracking-widest text-slate-500">Compare plans</span>
 240                      <div class="inline-flex rounded-full bg-slate-900 p-1 border border-slate-700 shadow-inner" role="tablist" aria-label="Free or Pro pricing">
 241                          <button type="button" id="plan-toggle-free" class="plan-toggle-btn plan-toggle-btn-inactive" aria-selected="false">Free</button>
 242                          <button type="button" id="plan-toggle-pro" class="plan-toggle-btn plan-toggle-btn-active" aria-selected="true">Pro plans</button>
 243                      </div>
 244                      <p id="plan-toggle-hint" class="text-xs text-slate-500 max-w-md">Showing paid plans highlighted. Tap <strong class="text-slate-400">Free</strong> to see the starter tier.</p>
 245                  </div>
 246              </div>
 247  
 248              <div id="pricing-compare" class="pricing-grid show-pro grid grid-cols-1 min-[500px]:grid-cols-2 lg:grid-cols-4 gap-4 sm:gap-6 items-stretch">
 249                  <div class="pricing-card pricing-card-free bg-slate-950 border border-slate-800 rounded-xl p-4 sm:p-6 flex flex-col min-w-0">
 250                      <h3 class="text-lg font-bold text-slate-300">Free</h3>
 251                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">&#8377;</span><span id="free-price">0</span></span></div>
 252                      <p class="text-xs text-slate-500 mb-6">Forever free.</p>
 253                      <ul class="space-y-3 mb-8 text-xs text-slate-400 flex-grow">
 254                          <li class="flex gap-2 text-red-400"><span>&#10005;</span> Watermark Forced</li>
 255                          <li class="flex gap-2 text-amber-400"><span>&#9888;</span> 3 Generations / Day</li>
 256                          <li class="flex gap-2 text-red-400"><span>&#10005;</span> Ads Visible</li>
 257                      </ul>
 258                      <button class="w-full py-2 border border-slate-700 rounded-lg text-sm text-slate-400 cursor-default">Current Plan</button>
 259                      <p class="text-[10px] sm:text-xs text-slate-500 text-center mt-3 pt-3 border-t border-slate-800/80 leading-relaxed">7-day free trial with promo code or referral code</p>
 260                  </div>
 261  
 262                  <div class="pricing-card pricing-card-paid bg-slate-900 border-2 border-blue-600/50 rounded-xl p-4 sm:p-6 flex flex-col min-w-0 hover:border-blue-500 transition shadow-lg shadow-blue-900/10">
 263                      <h3 class="text-lg font-bold text-blue-400">Weekly</h3>
 264                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">&#8377;</span><span id="weekly-price">93</span></span></div>
 265                      <p class="text-xs text-blue-200/90 mb-2 leading-snug font-medium">Perfect for small projects</p>
 266                      <div id="weekly-per-day" class="text-xs text-blue-300 mb-6 font-mono flex items-center gap-1">&#8377;13 / day</div>
 267                      <ul class="space-y-3 mb-8 text-xs text-slate-300 flex-grow">
 268                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> Remove Watermark</li>
 269                          <li class="flex gap-2 text-white"><span>&#128640;</span> <b>10 Gens / Day</b></li>
 270                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> No Ads</li>
 271                      </ul>
 272                      <a href="https://app.creatorsuiteai.org/signup?plan=weekly" class="w-full py-2 bg-blue-600 hover:bg-blue-500 text-white text-center rounded-lg text-sm font-bold transition shadow-lg shadow-blue-900/25">Buy Weekly</a>
 273                  </div>
 274  
 275                  <div class="pricing-card pricing-card-paid pricing-card-popular bg-slate-900 border-2 border-purple-600/50 rounded-xl p-4 sm:p-6 relative flex flex-col min-w-0 shadow-lg shadow-purple-900/10">
 276                      <div class="absolute top-0 right-0 bg-purple-600 text-white text-[10px] font-bold px-2 py-1 rounded-bl-lg">POPULAR</div>
 277                      <h3 class="text-lg font-bold text-purple-400">Monthly</h3>
 278                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">&#8377;</span><span id="monthly-price">235</span></span></div>
 279                      <p class="text-xs text-purple-200/90 mb-2 leading-snug font-medium">Flexibility for growing creators</p>
 280                      <div id="monthly-per-day" class="text-xs text-purple-300 mb-6 font-mono flex items-center gap-1">&#8377;8 / day</div>
 281                      <ul class="space-y-3 mb-8 text-xs text-white flex-grow">
 282                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> Remove Watermark</li>
 283                          <li class="flex gap-2 text-white"><span>&#128293;</span> <b>15 Gens / Day</b></li>
 284                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> No Ads</li>
 285                      </ul>
 286                      <a href="https://app.creatorsuiteai.org/signup?plan=monthly" class="w-full py-2 bg-purple-600 hover:bg-purple-500 text-center rounded-lg text-sm font-bold text-white transition">Buy Monthly</a>
 287                  </div>
 288  
 289                  <div class="pricing-card pricing-card-paid bg-slate-900 border-2 border-emerald-500 rounded-xl p-4 sm:p-6 flex flex-col relative min-w-0 lg:-translate-y-4 shadow-xl shadow-emerald-900/20">
 290                       <div class="bg-emerald-500 text-slate-900 text-[10px] sm:text-xs font-bold text-center py-1 -mx-4 -mt-4 sm:-mx-6 sm:-mt-6 mb-4 sm:mb-6 rounded-t-lg sm:rounded-t-xl">
 291                          GET 4 MONTHS FREE
 292                      </div>
 293                      <h3 class="text-lg font-bold text-emerald-400">Yearly</h3>
 294                      <div class="my-3"><span class="text-3xl font-bold text-white"><span class="currency-symbol">&#8377;</span><span id="yearly-price">1,769</span></span></div>
 295                      <p id="yearly-value-line" class="text-xs text-emerald-200/95 mb-1 leading-snug font-medium">Best value: ~&#8377;4.9/day &middot; Save ~37% vs 12&times; monthly</p>
 296                      <p class="text-[10px] font-bold uppercase tracking-wide text-emerald-100/90 mb-2">Early-adopter rates</p>
 297                      <div id="yearly-per-day" class="text-xs text-emerald-300 mb-6 font-mono flex items-center gap-1">&#8377;5 / day</div>
 298                      <ul class="space-y-3 mb-8 text-xs text-slate-300 flex-grow">
 299                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> Remove Watermark</li>
 300                          <li class="flex gap-2 text-white"><span>&#128081;</span> <b>15 Gens / Day</b></li>
 301                          <li class="flex gap-2 text-emerald-400"><span>&#10003;</span> No Ads</li>
 302                      </ul>
 303                      <a href="https://app.creatorsuiteai.org/signup?plan=yearly" class="w-full py-2 bg-emerald-600 hover:bg-emerald-500 text-slate-900 text-center rounded-lg text-sm font-bold transition">Buy Yearly</a>
 304                  </div>
 305              </div>
 306              <p class="text-center text-xs text-slate-600 mt-8">Prices inclusive of taxes. Cancel anytime. <span class="text-slate-500">Email support:</span> <a href="mailto:support@creatorsuiteai.org" class="text-blue-500 hover:text-blue-400">support@creatorsuiteai.org</a></p>
 307          </div>
 308      </section>
 309  
 310      <footer class="py-8 sm:py-10 text-center text-xs sm:text-sm text-slate-500 px-4">
 311      <div class="mb-4">
 312          &copy; <script>document.write(new Date().getFullYear())</script> CreatorSuite AI. 
 313          <span class="text-slate-400">A CreatorCanvas brand.</span>
 314      </div>
 315      
 316      <div class="footer-links flex flex-wrap justify-center gap-3 sm:gap-6">
 317             <a href="legal.html#privacy" class="hover:text-white transition">Privacy Policy</a>
 318             <a href="legal.html#terms" class="hover:text-white transition">Terms of Service</a>
 319             <a href="legal.html#refunds" class="hover:text-white transition">Refund Policy</a>
 320             <a href="legal.html#contact" class="hover:text-white transition">Contact Us</a>
 321      </div>
 322  
 323      <div class="flex flex-wrap justify-center gap-3 sm:gap-6 mt-4 text-xs font-medium">
 324          <a href="mailto:support@creatorsuiteai.org" class="text-blue-500 hover:text-blue-400 flex items-center gap-1 transition">
 325              <span class="opacity-50 text-slate-400">Need Help?</span> support@creatorsuiteai.org
 326          </a>
 327          <a href="mailto:security@creatorsuiteai.org" class="text-emerald-500 hover:text-emerald-400 flex items-center gap-1 transition">
 328              <span class="opacity-50 text-slate-400">Security:</span> security@creatorsuiteai.org
 329          </a>
 330      </div>
 331  </footer>
 332  
 333  <script>
 334  async function setGlobalPricing() {
 335      try {
 336          var cc = '';
 337          try {
 338              const r1 = await fetch('https://ipapi.co/json/?fields=country_code', { cache: 'no-store' });
 339              if (r1.ok) {
 340                  const d1 = await r1.json();
 341                  cc = String(d1.country_code || '').toUpperCase();
 342              }
 343          } catch (e1) { /* try fallback */ }
 344          if (!cc) {
 345              try {
 346                  const r2 = await fetch('https://get.geojs.io/v1/ip/country.json', { cache: 'no-store' });
 347                  if (r2.ok) {
 348                      const d2 = await r2.json();
 349                      cc = String(d2.country || '').toUpperCase();
 350                  }
 351              } catch (e2) { /* keep cc empty */ }
 352          }
 353          if (cc === 'IN') return;
 354          document.querySelectorAll('.currency-symbol').forEach(function (el) { el.textContent = '$'; });
 355          var fp = document.getElementById('free-price');
 356          if (fp) fp.textContent = '0';
 357          if (document.getElementById('weekly-price')) document.getElementById('weekly-price').textContent = '9';
 358          if (document.getElementById('monthly-price')) document.getElementById('monthly-price').textContent = '25';
 359          if (document.getElementById('yearly-price')) document.getElementById('yearly-price').textContent = '95';
 360          if (document.getElementById('weekly-per-day')) document.getElementById('weekly-per-day').textContent = '$1.29 / day';
 361          if (document.getElementById('monthly-per-day')) document.getElementById('monthly-per-day').textContent = '$0.83 / day';
 362          if (document.getElementById('yearly-per-day')) document.getElementById('yearly-per-day').textContent = '$0.26 / day';
 363          var yvl = document.getElementById('yearly-value-line');
 364          if (yvl) yvl.textContent = 'Best value: ~26\u00a2/day \u00b7 Save ~68% vs 12\u00d7 monthly';
 365          var lp = document.getElementById('league-prize');
 366          if (lp) lp.textContent = 'Win $12 + Lifetime Pro';
 367      } catch (e) { console.log('Defaulting to INR', e); }
 368  }
 369  document.addEventListener('DOMContentLoaded', function() {
 370      setGlobalPricing();
 371      var wrap = document.getElementById('pricing-compare');
 372      var btnFree = document.getElementById('plan-toggle-free');
 373      var btnPro = document.getElementById('plan-toggle-pro');
 374      var hint = document.getElementById('plan-toggle-hint');
 375      function setProMode(on) {
 376          if (!wrap) return;
 377          if (on) { wrap.classList.add('show-pro'); } else { wrap.classList.remove('show-pro'); }
 378          if (btnFree && btnPro) {
 379              if (on) {
 380                  btnPro.classList.add('plan-toggle-btn-active'); btnPro.classList.remove('plan-toggle-btn-inactive');
 381                  btnFree.classList.remove('plan-toggle-btn-active'); btnFree.classList.add('plan-toggle-btn-inactive');
 382                  btnPro.setAttribute('aria-selected', 'true'); btnFree.setAttribute('aria-selected', 'false');
 383              } else {
 384                  btnFree.classList.add('plan-toggle-btn-active'); btnFree.classList.remove('plan-toggle-btn-inactive');
 385                  btnPro.classList.remove('plan-toggle-btn-active'); btnPro.classList.add('plan-toggle-btn-inactive');
 386                  btnFree.setAttribute('aria-selected', 'true'); btnPro.setAttribute('aria-selected', 'false');
 387              }
 388          }
 389          if (hint) hint.innerHTML = on
 390              ? 'Paid plans highlighted. Tap <strong class="text-slate-400">Free</strong> to compare the starter tier.'
 391              : 'Free tier highlighted. Tap <strong class="text-slate-400">Pro plans</strong> to see Weekly, Monthly &amp; Yearly.';
 392      }
 393      if (btnFree) btnFree.addEventListener('click', function() { setProMode(false); });
 394      if (btnPro) btnPro.addEventListener('click', function() { setProMode(true); });
 395  });
 396  </script>
 397  </body>
 398  </html>

/* ===== legal.html ===== */
   1  <!DOCTYPE html>
   2  <html lang="en">
   3  <head>
   4      <meta charset="UTF-8">
   5      <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, viewport-fit=cover">
   6      <title>Legal & Compliance | CreatorSuite</title>
   7      <script src="https://cdn.tailwindcss.com"></script>
   8      <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
   9      <style>
  10          * { box-sizing: border-box; }
  11          body { word-wrap: break-word; }
  12          .legal-section p, .legal-section li { overflow-wrap: break-word; }
  13      </style>
  14  </head>
  15  <body class="bg-slate-950 text-slate-300 font-sans antialiased p-4 sm:p-8 md:p-20 overflow-x-hidden">
  16  
  17      <div class="max-w-4xl mx-auto legal-section">
  18          <a href="creatorsuite.html" class="text-blue-500 hover:text-blue-400 mb-8 block">← Back to Website</a>
  19          
  20          <h1 class="text-4xl font-bold text-white mb-4">Legal & Compliance Center</h1>
  21  
  22          <section class="mb-16 border-b border-slate-800 pb-12" id="privacy">
  23              <h2 class="text-2xl font-bold text-white mb-6">🔒 Privacy Policy</h2>
  24              <div class="space-y-4 text-sm leading-relaxed">
  25                  <p><strong>1. Data Fiduciary & Controller</strong><br>
  26                  CreatorCanvas ("Company", "We") is the Data Fiduciary under the Digital Personal Data Protection Act, 2023 (India).</p>
  27                  
  28                  <p><strong>2. Introduction</strong><br>
  29                  Welcome to CreatorSuite (the "App"). We are committed to protecting your privacy.</p>
  30  
  31                  <p><strong>3. Data We Collect</strong><br>
  32                  - <strong>Account Data:</strong> Name, Email (for Pro subscription management).<br>
  33                  - <strong>AI "DNA Profile":</strong> User-defined brand voice, stylistic preferences, and specific content DNA used to personalize AI outputs.<br>
  34                  - <strong>Payment Data:</strong> We do NOT store card details. All transactions are processed via Razorpay/Paytm/Lemon Squeezy (PCI-DSS Compliant).<br>
  35                  - <strong>Usage Data:</strong> We track AI feature usage to improve output quality.</p>
  36                  
  37                  <p><strong>4. AI & Content Ownership</strong><br>
  38                  - <strong>Your Inputs:</strong> Text/Images uploaded are processed by AI solely to generate results.<br>
  39                  - <strong>Your Ownership:</strong> You own 100% of the intellectual property (scripts, captions, contracts) generated using this tool.</p>
  40  
  41                  <p><strong>5. AI "DNA Profile" Protections & Encryption</strong><br>
  42                  - <strong>Strict Isolation:</strong> Your "DNA Profile" is protected by <strong>Row Level Security (RLS)</strong>. No other user can view or access your specific stylistic data.<br>
  43                  - <strong>Encryption:</strong> All DNA records are encrypted <strong>at rest</strong> using industry-standard AES-256 encryption within our [CLOUD DATABASE PROVIDER] production infrastructure.<br>
  44                  - <strong>Data Preservation:</strong> DNA records are preserved in your secure database profile to ensure consistency in AI outputs. You may request deletion of this data at any time.</p>
  45              </div>
  46          </section>
  47  
  48          <section class="mb-16 border-b border-slate-800 pb-12" id="terms">
  49              <h2 class="text-2xl font-bold text-white mb-6">📜 Terms of Service & Liability Waiver</h2>
  50              <div class="p-4 bg-yellow-900/10 border border-yellow-500/20 rounded-lg text-sm mb-6">
  51                  <strong>Notice:</strong> By using this App, you agree to the following strictly enforced terms.
  52              </div>
  53  
  54              <div class="space-y-4 text-sm leading-relaxed">
  55                  <p><strong>1. Nature of Service (The 'Tool' Clause)</strong><br>
  56                  CreatorSuite is an AI-powered software tool for information purposes only. We are NOT a law firm. The documents generated are drafts/templates and do not constitute legal advice.</p>
  57                  
  58                  <p><strong>2. Global Compliance</strong><br>
  59                  You agree to comply with all applicable local, state, and international laws. You are solely responsible for ensuring that any content generated via this App complies with the laws of your specific region.</p>
  60  
  61                  <p><strong>3. Limitation of Liability</strong><br>
  62                  To the maximum extent permitted by law, CreatorCanvas, its Proprietor (Owner), and Affiliates shall NOT be liable for any direct, indirect, or consequential damages arising from errors, omissions, or missing clauses in generated documents. Total liability is limited to fees paid by you in the last 12 months.</p>
  63                  
  64                  <p><strong>4. Indemnification</strong><br>
  65                  You agree to indemnify and hold CreatorCanvas, its Proprietor (Owner) and Affiliates harmless from any claims resulting from your use of the generated documents.</p>
  66  
  67                  <p><strong>5. Pricing & Subscription Terms</strong><br>
  68                  Since our services rely on third-party AI infrastructure costs, pricing is subject to change without prior notice. However, any active subscription will be honored at its original rate until the end of the current billing cycle. Future renewals and new subscriptions will be charged at the rates effective at the time of payment.</p>
  69  
  70                  <p><strong>6. Third-Party Disputes & No Recourse</strong><br>
  71                  - <strong>Sole Liability:</strong> In the event of any legal action between You and any Third Party arising from a document generated by this App, You shall be the sole party liable.<br>
  72                  - <strong>No Recourse:</strong> You explicitly waive any right to seek compensation or contribution from CreatorSuite.</p>
  73  
  74                  <p><strong>7. AI Unpredictability & Technical Malfunction (CRITICAL)</strong><br>
  75                  - <strong>No Malicious Intent:</strong> You acknowledge that the App is designed with positive intent. However, Artificial Intelligence is inherently probabilistic and may occasionally produce "hallucinations," errors, or unintended outputs ("Misbehavior").<br>
  76                  - <strong>Assumption of Risk:</strong> You accept that any such "misbehavior," omission, or commission by the App is a technical limitation of AI technology, not a malicious act by the Developer.<br>
  77                  - <strong>Total Waiver:</strong> You agree that the Developer shall bear NO LIABILITY for any actions taken by you based on such unintended App behavior. You are solely responsible for verifying all outputs.</p>
  78  
  79                  <p><strong>8. Refund Policy & Account Suspension</strong><br>
  80                  - <strong>Termination for Breach:</strong> We reserve the right to ban or suspend any account found violating these Terms, including generating illegal content, abusing the referral system, or attempting to reverse-engineer the platform.<br>
  81                  - <strong>Effect of Ban:</strong> If your account is banned for a violation of these Terms, you forfeit all remaining subscription time and credits.</p>
  82  
  83                  <p><strong>9. Governing Law, Jurisdiction, and Mandatory Law Carve-Out</strong><br>
  84                  These Terms are governed by the laws of India. Subject to applicable mandatory consumer-protection law, the courts at New Delhi, India, shall have exclusive jurisdiction over disputes arising from or related to the App, payments, subscriptions, and generated outputs. Where non-waivable local law grants a consumer the right to file in local forums, that right will apply only to the minimum extent required by such law.</p>
  85  
  86                  <p><strong>10. Policy Version and Regulatory Override</strong><br>
  87                  The policy/version in force at the time of purchase applies to that purchase, except where a later law, regulation, court order, or binding government direction requires a different outcome. In such cases, we will comply with mandatory law to the extent required.</p>
  88              </div>
  89          </section>
  90  
  91          <section class="mb-16 border-b border-slate-800 pb-12" id="disclaimer">
  92              <h2 class="text-2xl font-bold text-white mb-6">⚠️ AI Disclaimer</h2>
  93              <div class="p-4 bg-blue-900/10 border border-blue-500/20 rounded-lg text-sm">
  94                  <p><strong>Important:</strong> CreatorSuite uses Large Language Models (LLMs) to generate text and scripts.</p>
  95                  <ul class="list-disc pl-5 mt-2 space-y-1">
  96                      <li>AI can make mistakes (hallucinations). Always review content before posting.</li>
  97                      <li>You own the content you generate, but we claim no ownership over AI outputs.</li>
  98                      <li>The "Viral Trends" feature is based on available data and does not guarantee viral success.</li>
  99                  </ul>
 100              </div>
 101          </section>
 102  
 103          <section class="mb-16 border-b border-slate-800 pb-12" id="refunds">
 104              <h2 class="text-2xl font-bold text-white mb-6">💰 Refund & Cancellation Policy</h2>
 105              <div class="space-y-4 text-sm leading-relaxed">
 106                  <p><strong>1. Digital Product Consumption</strong><br>
 107                  CreatorSuite AI operates on a credit-based system. A refund is only eligible if requested within <strong>7 days of purchase</strong>, provided that <strong>zero (0) AI credits</strong> have been utilized. Our system maintains an immutable <code>credit_usage_ledger</code>; if <strong>any credits are consumed through any app action/output</strong>, the plan is considered consumed and ineligible for refund.</p>
 108  
 109                  <p><strong>2. Processing Fees</strong><br>
 110                  All eligible refunds are subject to a <strong>3% transaction processing fee</strong> deduction to cover non-refundable gateway commissions.</p>
 111  
 112                  <p><strong>3. Government Taxes, Duties, and Levies</strong><br>
 113                  Any <strong>taxes, duties, withholding, or government levies</strong> (including GST, VAT, sales tax, or similar) that were collected, remitted, or withheld in connection with your payment are <strong>not refundable by us in any case</strong>, regardless of the reason for any refund of subscription fees or credits, <strong>except where applicable mandatory law expressly requires otherwise</strong>.</p>
 114  
 115                  <p><strong>4. Technical Failure & Activation Guarantee</strong><br>
 116                  If your payment is successful but the subscription is not activated due to a system error, our first priority is to <strong>manually activate your plan</strong> within 24 hours of notification. If we are unable to resolve the activation within 5 business days, a full refund will be issued to your original payment method.</p>
 117  
 118                  <p><strong>5. Duplicate Charges</strong><br>
 119                  In the event of accidental double-billing for the same period <strong>for the same account</strong>, the second charge will be refunded within 5-7 business days upon verification.</p>
 120  
 121                  <p><strong>6. No Partial Refund After Consumption</strong><br>
 122                  Except where required by applicable mandatory law, partial or prorated refunds are not available once any credits are consumed.</p>
 123  
 124                  <p><strong>7. Dispute Notice Timelines</strong><br>
 125                  Refund requests based on non-usage must be raised within <strong>7 days</strong> of payment. Other billing disputes must be raised within <strong>30 days</strong> of the charge date. Disputes raised after 30 days will be declined, except where applicable mandatory law requires otherwise.</p>
 126  
 127                  <p><strong>8. Usage Records and Evidence</strong><br>
 128                  We maintain system records including authentication events, timestamps, plan activations, and credit consumption logs (including <code>credit_usage_ledger</code>) for support, security, and dispute handling. Detailed logs are retained for a limited operational period of <strong>30 to 35 days</strong> to manage infrastructure cost and operational efficiency, and our records are treated as authoritative unless proven otherwise with reliable evidence.</p>
 129  
 130                  <p><strong>9. Fraud, Abuse, Chargebacks, and Cost Recovery</strong><br>
 131                  We may, at our sole reasonable discretion, investigate and take operational action (including suspension, termination, access restriction, refund denial, and benefit forfeiture) against accounts involved in suspected fraud, abusive refund/chargeback behavior, misrepresentation, or attempts to obtain services without payment. Where abuse, fraud, or bad-faith conduct is established through applicable legal process (including court, arbitration, or other competent forum), we reserve the right to seek recovery of reasonable legal costs, administrative costs, and damages to the maximum extent permitted by law. This clause does not limit a user’s non-waivable legal rights under mandatory law.</p>
 132              </div>
 133          </section>
 134  
 135          <section class="mb-16" id="contact">
 136              <h2 class="text-2xl font-bold text-white mb-6">📧 Contact Us</h2>
 137              <div class="space-y-4 text-sm leading-relaxed">
 138                  <p>For support, billing inquiries, or grievance redressal:</p>
 139                  <ul class="space-y-2">
 140                      <li><strong>Email:</strong> support@creatorsuiteai.org</li>
 141                      <li><strong>Operational Address:</strong> [REDACTED FOR PRIVACY], New Delhi - 110060, India</li>
 142                      <li><strong>Support Hours:</strong> Mon-Fri, 10 AM - 6 PM IST</li>
 143                  </ul>
 144              </div>
 145          </section>
 146          
 147          <div class="text-center text-xs text-slate-600 mt-20">
 148              © 2025-2026 CreatorCanvas. All Rights Reserved. |  Jan 8, 2026
 149          </div>
 150      </div>
 151  </body>
 152  </html>
```
