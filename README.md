<!DOCTYPE html>
<html lang="fr" class="h-full bg-slate-900 text-slate-100">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Sous le manteau de Saint Joseph</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="min-h-full flex flex-col justify-between selection:bg-amber-500 selection:text-black">

  <!-- 1. CADRE EN-TÊTE (FIXE EN HAUT) -->
  <header class="sticky top-0 z-50 bg-black/90 backdrop-blur-md border-b border-slate-800 px-4 py-3 shadow-md">
    <div class="max-w-xl mx-auto flex items-center justify-between">
      <h1 class="text-lg font-bold tracking-wide text-white">Sous le manteau de Saint Joseph</h1>
      <div class="flex items-center space-x-2">
        <!-- Bouton Haut-Parleur (Blanc sur Noir) -->
        <button class="w-9 h-9 flex items-center justify-center rounded-full bg-black text-white border border-slate-700 hover:border-white transition">
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.536 8.464a5 5 0 010 7.072M18.364 5.636a9 9 0 010 12.728M11 5L6 9H2v6h4l5 4V5z"/></svg>
        </button>
        <!-- Bouton Lumière (Blanc sur Noir) -->
        <button class="w-9 h-9 flex items-center justify-center rounded-full bg-black text-white border border-slate-700 hover:border-white transition">
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v1m0 16v1m9-9h-1M4 12H3m15.364 6.364l-.707-.707M6.343 6.343l-.707-.707m12.728 0l-.707.707M6.343 17.657l-.707.707M16 12a4 4 0 11-8 0 4 4 0 018 0z"/></svg>
        </button>
      </div>
    </div>
  </header>

  <!-- CONTENU PRINCIPAL CONTAINER -->
  <main class="flex-grow w-full max-w-xl mx-auto px-4 py-6 space-y-8">

    <!-- 2. CADRE TABLEAU SAINT-JOSEPH (IMAGE + PASTILLES FIXES) -->
    <section class="relative w-full bg-slate-800 rounded-2xl border border-slate-700 shadow-2xl overflow-hidden select-none">
      <div class="p-4 border-b border-slate-700/50">
        <h2 class="text-md font-semibold text-amber-400">Tableau de Saint Joseph</h2>
      </div>
      
      <!-- Zone d'image verrouillée -->
      <div class="relative w-full bg-black touch-none">
        <img src="votre-image-saint-joseph.jpg" alt="Saint Joseph" class="w-full h-auto block pointer-events-none select-none">

        <!-- Pastille Jaune -->
        <button class="absolute w-7 h-7 rounded-full bg-yellow-400 border-2 border-white shadow-lg transform -translate-x-1/2 -translate-y-1/2 focus:outline-none" style="top: 25%; left: 40%;"></button>
        <!-- Pastille Bleue -->
        <button class="absolute w-7 h-7 rounded-full bg-blue-500 border-2 border-white shadow-lg transform -translate-x-1/2 -translate-y-1/2 focus:outline-none" style="top: 55%; left: 30%;"></button>
        <!-- Pastille Rouge -->
        <button class="absolute w-7 h-7 rounded-full bg-red-500 border-2 border-white shadow-lg transform -translate-x-1/2 -translate-y-1/2 focus:outline-none" style="top: 70%; left: 65%;"></button>
        <!-- Pastille Verte (BibleWalks) -->
        <a href="https://www.biblewalks.com/nazareth_maps/" target="_blank" rel="noopener noreferrer" class="absolute w-7 h-7 rounded-full bg-emerald-500 border-2 border-white shadow-lg transform -translate-x-1/2 -translate-y-1/2 flex items-center justify-center focus:outline-none" style="top: 40%; left: 75%;"></a>
      </div>

      <!-- Sources intégrées au cadre -->
      <div class="p-3 bg-slate-800/80 border-t border-slate-700 text-xs text-slate-400 flex justify-between items-center">
        <span>Source : Google Arts & Culture</span>
        <a href="https://www.biblewalks.com/nazareth_maps/" target="_blank" class="text-emerald-400 hover:underline">BibleWalks Maps</a>
      </div>
    </section>

    <!-- 3. CADRE NEUVAINE À SAINT-JOSEPH -->
    <section class="relative w-full bg-slate-800 rounded-2xl border border-slate-700 shadow-xl overflow-hidden p-5 space-y-3">
      <h2 class="text-lg font-bold text-amber-400 border-b border-slate-700 pb-2">Neuvaine à Saint Joseph</h2>
      <div class="text-sm text-slate-300 leading-relaxed space-y-2">
        <p>Saint Joseph, père nourricier de Jésus et époux de la Vierge Marie, je me tourne vers toi avec confiance...</p>
      </div>
    </section>

    <!-- 4. CADRE NAZARETH -->
    <section class="relative w-full bg-slate-800 rounded-2xl border border-slate-700 shadow-xl overflow-hidden p-5 space-y-3">
      <h2 class="text-lg font-bold text-emerald-400 border-b border-slate-700 pb-2">Nazareth & Contexte Historique</h2>
      <p class="text-sm text-slate-300 leading-relaxed">
        Découvrez les cartes et emplacements historiques liés à la vie de la Sainte Famille à Nazareth.
      </p>
      <a href="https://www.biblewalks.com/nazareth_maps/" target="_blank" rel="noopener noreferrer" class="inline-block mt-2 px-4 py-2 bg-emerald-600 text-white text-xs font-semibold rounded-lg shadow hover:bg-emerald-500 transition">
        Consulter les cartes Nazareth sur BibleWalks
      </a>
    </section>

  </main>

  <!-- 5. CADRE PIED DE PAGE (PROPRIÉTÉ INTELLECTUELLE) -->
  <footer class="w-full bg-black border-t border-slate-800 py-6 px-4 text-center text-xs text-slate-500">
    <div class="max-w-xl mx-auto space-y-1">
      <p>© 2026 Sous le manteau de Saint Joseph — Tous droits réservés.</p>
      <p class="text-slate-600">Conception et droits de propriété intellectuelle protégés.</p>
    </div>
  </footer>

</body>
</html>
