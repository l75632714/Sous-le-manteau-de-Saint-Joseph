<!DOCTYPE html>
<html lang="fr" class="h-full bg-amber-50">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sous le manteau de Saint-Joseph</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Fonts: Lora Bold & Inter -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Lora:ital,wght@0,700;1,700&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Inter', sans-serif;
    }
    .font-lora-bold {
      font-family: 'Lora', serif;
      font-weight: 700;
    }
    
    /* Lumière apaisante (Fond tamisé) */
    .soothing-mode {
      background-color: #1c1917 !important;
      color: #f5f5f4 !important;
    }
    .soothing-mode .bg-card {
      background-color: #292524 !important;
      border-color: #44403c !important;
      color: #f5f5f4 !important;
    }
    .soothing-mode .text-muted {
      color: #d6d3d1 !important;
    }
    .soothing-mode .header-bg {
      background-color: #0c0a09 !important;
      border-bottom-color: #292524 !important;
    }

    /* Halo interactif au survol de Saint-Joseph */
    .halo-effect {
      filter: drop-shadow(0 0 10px rgba(234, 179, 8, 0.3));
      transition: all 0.5s ease;
    }
    .halo-container:hover .halo-effect {
      filter: drop-shadow(0 0 28px rgba(234, 179, 8, 0.8));
    }
    .halo-container:hover .halo-ring {
      opacity: 0.95;
      transform: scale(1.03);
    }
    .halo-ring {
      transition: all 0.5s ease;
      transform-origin: center;
    }
  </style>
</head>
<body class="h-full text-stone-800 transition-colors duration-500">

  <div id="app" class="min-h-screen flex flex-col justify-between">
    
    <!-- En-tête -->
    <header class="header-bg bg-amber-900/95 text-amber-50 shadow-md border-b border-amber-800/50 sticky top-0 z-50 transition-colors duration-500">
      <div class="max-w-4xl mx-auto px-4 py-4 flex flex-wrap justify-between items-center gap-4">
        
        <!-- Titre principal de l'application -->
        <h1 class="font-lora-bold text-xl md:text-2xl tracking-wide text-amber-100 flex items-center gap-2">
          Sous le manteau de Saint-Joseph
        </h1>

        <!-- Barres d'outils et options -->
        <div class="flex items-center gap-3">
          
          <!-- Menu déroulant : Saint-Joseph dans l'année -->
          <div class="relative inline-block text-left">
            <select id="feasts-select" class="bg-amber-800/80 hover:bg-amber-800 text-amber-100 text-sm font-medium py-2 px-3 rounded-lg border border-amber-700/60 focus:outline-none focus:ring-2 focus:ring-amber-400 transition cursor-pointer">
              <option value="" disabled selected>Saint-Joseph dans l'année</option>
              <option value="19mars">19 Mars — Ave Joseph</option>
              <option value="1mai">1er Mai — Prière du Travailleur</option>
            </select>
          </div>

          <!-- Bouton Ambiance de la Colombe 🕊️ -->
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance de la Colombe" class="p-2 rounded-lg bg-amber-800/80 hover:bg-amber-800 border border-amber-700/60 text-amber-100 transition flex items-center gap-1.5 text-sm">
            <span>🕊️</span>
            <span id="dove-status" class="hidden md:inline text-xs">Ambiance</span>
          </button>

          <!-- Bouton Lumière apaisante -->
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-2 rounded-lg bg-amber-800/80 hover:bg-amber-800 border border-amber-700/60 text-amber-100 transition flex items-center gap-1 text-sm">
            <span>💡</span>
          </button>

        </div>
      </div>
    </header>

    <!-- Contenu Principal -->
    <main class="max-w-4xl mx-auto px-4 py-8 flex-grow space-y-10 w-full">

      <!-- Section Nazareth & Illustration SVG interactive -->
      <section class="bg-card bg-white rounded-2xl p-6 md:p-8 shadow-sm border border-amber-200/60 transition-colors duration-500">
        
        <h2 class="font-lora-bold text-2xl md:text-3xl text-amber-900 mb-6 text-center">
          Nazareth
        </h2>

        <!-- Illustration SVG interactive de Saint-Joseph avec nimbes lisses -->
        <div class="halo-container max-w-sm mx-auto mb-8 cursor-pointer flex flex-col items-center">
          <svg viewBox="0 0 400 400" class="w-64 h-64 md:w-80 md:h-80 halo-effect rounded-full shadow-lg bg-gradient-to-b from-amber-950 via-stone-900 to-amber-950">
            <defs>
              <!-- Dégradés dorés lisses pour les nimbes -->
              <radialGradient id="halo-joseph" cx="50%" cy="50%" r="50%">
                <stop offset="0%" stop-color="#fef08a" stop-opacity="0.9" />
                <stop offset="70%" stop-color="#eab308" stop-opacity="0.8" />
                <stop offset="100%" stop-color="#ca8a04" stop-opacity="0" />
              </radialGradient>
              
              <linearGradient id="gold-smooth" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" stop-color="#fef08a" />
                <stop offset="50%" stop-color="#eab308" />
                <stop offset="100%" stop-color="#a16207" />
              </linearGradient>

              <linearGradient id="mantle-grad" x1="0%" y1="0%" x2="0%" y2="100%">
                <stop offset="0%" stop-color="#78350f" />
                <stop offset="100%" stop-color="#451a03" />
              </linearGradient>

              <linearGradient id="tunic-grad" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stop-color="#15803d" />
                <stop offset="100%" stop-color="#166534" />
              </linearGradient>
            </defs>

            <!-- Lueur d'ambiance réactive -->
            <circle cx="200" cy="180" r="160" fill="url(#halo-joseph)" class="halo-ring opacity-70" />

            <!-- Nimbe de Saint-Joseph (Lisse, sans motif ni gravure) -->
            <circle cx="185" cy="155" r="85" fill="none" stroke="url(#gold-smooth)" stroke-width="6" class="halo-ring opacity-90" />
            <circle cx="185" cy="155" r="82" fill="#fef08a" fill-opacity="0.15" />

            <!-- Nimbe de l'Enfant-Jésus (Lisse, sans motif ni gravure) -->
            <circle cx="255" cy="210" r="50" fill="none" stroke="url(#gold-smooth)" stroke-width="4" class="halo-ring opacity-90" />
            <circle cx="255" cy="210" r="48" fill="#fef08a" fill-opacity="0.15" />

            <!-- Silhouette classique : Saint-Joseph -->
            <!-- Tunique -->
            <path d="M120 360 C120 280, 140 220, 185 210 C210 215, 230 250, 240 360 Z" fill="url(#tunic-grad)" />
            <!-- Manteau -->
            <path d="M100 360 C100 250, 145 195, 185 195 C220 195, 260 230, 280 360 Z" fill="url(#mantle-grad)" opacity="0.9" />

            <!-- Visage de Saint-Joseph -->
            <path d="M160 135 C160 110, 210 110, 210 135 C210 165, 195 185, 185 185 C175 185, 160 165, 160 135 Z" fill="#fde047" opacity="0.2" />
            <ellipse cx="185" cy="150" rx="22" ry="28" fill="#f5d0fe" opacity="0.3" />
            <!-- Chevelure et barbe sobres -->
            <path d="M160 140 C155 120, 170 105, 185 105 C205 105, 215 120, 210 140 C205 130, 165 130, 160 140 Z" fill="#451a03" />
            <path d="M162 155 C160 185, 210 185, 208 155 C198 175, 172 175, 162 155 Z" fill="#382110" />

            <!-- Enfant-Jésus -->
            <path d="M220 360 C220 270, 280 250, 290 360 Z" fill="#fef3c7" />
            <ellipse cx="255" cy="210" rx="16" ry="20" fill="#fde047" opacity="0.25" />
            <path d="M242 205 C240 190, 270 190, 268 205 Z" fill="#78350f" />

            <!-- Ombrage général et douceur -->
            <circle cx="200" cy="200" r="190" fill="none" stroke="#ca8a04" stroke-width="2" opacity="0.4" />
          </svg>
          <span class="text-xs text-muted text-stone-500 mt-2 font-medium italic">Illustration interactive — Halo réactif au survol</span>
        </div>

        <p class="text-muted text-stone-700 leading-relaxed text-center max-w-2xl mx-auto">
          Découvrez la vie humble et silencieuse de la Sainte Famille à Nazareth. Sous la protection vigilante de Saint-Joseph, maître du travail accompli dans la foi et le silence, chaque foyer trouve un modèle de paix et de dévouement.
        </p>
      </section>

      <!-- Section Neuvaine Interactive -->
      <section class="bg-card bg-white rounded-2xl p-6 md:p-8 shadow-sm border border-amber-200/60 transition-colors duration-500">
        
        <div class="text-center mb-8">
          <h2 class="font-lora-bold text-2xl md:text-3xl text-amber-900 mb-2">
            Neuvaine interactive
          </h2>
          <p class="text-muted text-amber-800/90 font-medium text-sm md:text-base">
            Cocher chaque jour de votre neuvaine.
          </p>
        </div>

        <!-- Grille des 9 Jours -->
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <script>
            // Génération dynamique des 9 jours de la neuvaine
            for (let i = 1; i <= 9; i++) {
              document.write(`
                <label class="flex items-center p-4 rounded-xl border border-amber-100 bg-amber-50/50 hover:bg-amber-100/50 cursor-pointer transition">
                  <input type="checkbox" class="w-5 h-5 accent-amber-700 rounded focus:ring-amber-500">
                  <span class="ml-3 font-semibold text-amber-950">Jour ${i}</span>
                </label>
              `);
            }
          </script>
        </div>
      </section>

    </main>

    <!-- Pied de page -->
    <footer class="text-center py-6 text-xs text-muted text-stone-500 border-t border-amber-200/40">
      Sous le manteau de Saint-Joseph — Application de prière et de méditation
    </footer>

  </div>

  <!-- Script Web Audio API : Ambiance de la Colombe (Vent doux + Oiseaux) -->
  <script>
    let audioCtx = null;
    let isPlayingDove = false;
    let windGain = null;
    let birdInterval = null;

    function initAudio() {
      if (!audioCtx) {
        audioCtx = new (window.AudioContext || window.webkitAudioContext)();
      }
    }

    function toggleDoveSound() {
      initAudio();

      if (isPlayingDove) {
        stopDoveSound();
      } else {
        startDoveSound();
      }
    }

    function startDoveSound() {
      if (audioCtx.state === 'suspended') {
        audioCtx.resume();
      }
      
      isPlayingDove = true;
      document.getElementById('dove-btn').classList.add('bg-amber-700', 'ring-2', 'ring-amber-400');
      document.getElementById('dove-status').textContent = 'Actif';

      // 1. Génération du souffle de vent apaisant
      const bufferSize = audioCtx.sampleRate * 2;
      const noiseBuffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate);
      const output = noiseBuffer.getChannelData(0);
      for (let i = 0; i < bufferSize; i++) {
        output[i] = Math.random() * 2 - 1;
      }

      const whiteNoise = audioCtx.createBufferSource();
      whiteNoise.buffer = noiseBuffer;
      whiteNoise.loop = true;

      const filter = audioCtx.createBiquadFilter();
      filter.type = 'lowpass';
      filter.frequency.value = 300;

      windGain = audioCtx.createGain();
      windGain.gain.value = 0.08;

      whiteNoise.connect(filter);
      filter.connect(windGain);
      windGain.connect(audioCtx.destination);
      whiteNoise.start();

      // 2. Génération ponctuelle des paziements d'oiseaux
      birdInterval = setInterval(() => {
        if (isPlayingDove && Math.random() > 0.3) {
          playSoftChirp();
        }
      }, 3500);
    }

    function playSoftChirp() {
      if (!audioCtx || !isPlayingDove) return;

      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();

      osc.type = 'sine';
      const now = audioCtx.currentTime;
      const startFreq = 2200 + Math.random() * 600;
      
      osc.frequency.setValueAtTime(startFreq, now);
      osc.frequency.exponentialRampToValueAtTime(startFreq + 400, now + 0.1);
      osc.frequency.exponentialRampToValueAtTime(startFreq - 200, now + 0.25);

      gain.gain.setValueAtTime(0.01, now);
      gain.gain.linearRampToValueAtTime(0.04, now + 0.08);
      gain.gain.exponentialRampToValueAtTime(0.001, now + 0.25);

      osc.connect(gain);
      gain.connect(audioCtx.destination);

      osc.start(now);
      osc.stop(now + 0.25);
    }

    function stopDoveSound() {
      isPlayingDove = false;
      if (windGain) {
        windGain.gain.linearRampToValueAtTime(0.001, audioCtx.currentTime + 0.5);
      }
      if (birdInterval) {
        clearInterval(birdInterval);
      }
      document.getElementById('dove-btn').classList.remove('bg-amber-700', 'ring-2', 'ring-amber-400');
      document.getElementById('dove-status').textContent = 'Ambiance';
    }

    // Gestion du mode Lumière Apaisante
    function toggleSoothingLight() {
      document.body.classList.toggle('soothing-mode');
    }
  </script>
</body>
</html>
