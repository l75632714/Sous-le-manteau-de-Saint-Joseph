<!DOCTYPE html>
<html lang="fr" class="h-full bg-slate-50">
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

    /* Lumière apaisante (Mode Sombre Argent/Bleu Nuit) */
    .soothing-mode {
      background-color: #0f172a !important;
      color: #f8fafc !important;
    }
    .soothing-mode .bg-card {
      background-color: #1e293b !important;
      border-color: #334155 !important;
      color: #f8fafc !important;
    }
    .soothing-mode .header-bg {
      background-color: #020617 !important;
      border-bottom-color: #1e293b !important;
    }
    .soothing-mode .text-royal {
      color: #93c5fd !important;
    }
    .soothing-mode .border-silver {
      border-color: #334155 !important;
    }

    /* Halo interactif au survol de Saint-Joseph */
    .halo-effect {
      box-shadow: 0 0 15px rgba(212, 175, 55, 0.25);
      transition: all 0.5s ease;
    }
    .halo-container:hover .halo-effect {
      box-shadow: 0 0 35px rgba(212, 175, 55, 0.65);
      transform: scale(1.01);
    }

    /* Gradient personnalisé Argent / Doré / Bleu Royal */
    .bg-royal-header {
      background: linear-gradient(135deg, #0b192c 0%, #1e3e62 100%);
    }
    .text-gold {
      color: #d4af37;
    }
    .bg-gold {
      background-color: #d4af37;
    }
    .border-gold {
      border-color: #d4af37;
    }
  </style>
</head>
<body class="h-full text-slate-800 bg-slate-50 transition-colors duration-500">

  <div id="app" class="min-h-screen flex flex-col justify-between">
    
    <!-- En-tête Moderne Bleu Royal & Argent -->
    <header class="header-bg bg-royal-header text-white shadow-lg border-b border-slate-700/50 sticky top-0 z-50 transition-colors duration-500">
      <div class="max-w-7xl mx-auto px-6 py-4 flex flex-col items-center justify-center gap-4">
        
        <!-- Titre de l'application centré -->
        <h1 class="font-lora-bold text-2xl md:text-3xl tracking-wide text-amber-100 text-center">
          Sous le manteau de Saint-Joseph
        </h1>

        <!-- Controls Header centrés -->
        <div class="flex flex-wrap justify-center items-center gap-3 w-full">
          
          <!-- Menu 1 : Saint-Joseph dans l'année -->
          <select id="feasts-select" class="bg-slate-800/80 hover:bg-slate-700 text-slate-100 text-xs md:text-sm font-medium py-2 px-3 rounded-xl border border-slate-600/60 focus:outline-none focus:ring-2 focus:ring-amber-400 transition cursor-pointer">
            <option value="" disabled selected>Saint-Joseph dans l'année</option>
            <option value="19mars">19 Mars — Ave Joseph</option>
            <option value="1mai">1er Mai — Prière du Travailleur</option>
          </select>

          <!-- Menu 2 : Second menu déroulant Saint-Joseph avec Prières -->
          <select id="joseph-prayers-select" class="bg-amber-600/90 hover:bg-amber-500 text-slate-900 font-semibold text-xs md:text-sm py-2 px-3 rounded-xl border border-amber-400 focus:outline-none focus:ring-2 focus:ring-amber-300 transition cursor-pointer">
            <option value="" disabled selected>Saint-Joseph</option>
            <option value="19mars_ave">19 Mars — Ave Joseph</option>
            <option value="1mai_travailleur">1er Mai — Prière du Travailleur</option>
          </select>

          <!-- Bouton Colombe 🕊️ -->
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance de la Colombe" class="p-2.5 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 text-slate-100 transition flex items-center gap-1.5 text-xs md:text-sm">
            <span>🕊️</span>
            <span id="dove-status" class="hidden md:inline text-xs">Ambiance</span>
          </button>

          <!-- Bouton Lumière apaisante 💡 -->
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-2.5 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 text-slate-100 transition flex items-center text-xs md:text-sm">
            <span>💡</span>
          </button>

        </div>
      </div>
    </header>

    <!-- Layout Principal : Menu Neuvaine à gauche (fin et long), Contenu à droite -->
    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8">
      
      <!-- Panneau Latéral Gauche : Neuvaine Interactive (Fin, Long, Épuré) -->
      <aside class="w-full md:w-72 flex-shrink-0">
        <div class="bg-card bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 sticky top-28 transition-colors duration-500">
          <div class="mb-6 text-center md:text-left border-b border-slate-100 pb-4">
            <h2 class="font-lora-bold text-xl text-slate-900 text-royal mb-1">
              Neuvaine interactive
            </h2>
            <p class="text-xs text-slate-500 font-medium italic">
              Cocher chaque jour de votre neuvaine.
            </p>
          </div>

          <!-- Liste verticale fine des 9 jours -->
          <div class="space-y-2.5">
            <script>
              for (let i = 1; i <= 9; i++) {
                document.write(`
                  <label class="flex items-center justify-between p-3 rounded-xl border border-slate-100 bg-slate-50/60 hover:bg-amber-50/40 hover:border-amber-200/60 cursor-pointer transition group">
                    <span class="text-sm font-medium text-slate-700 group-hover:text-slate-900">Jour ${i}</span>
                    <input type="checkbox" class="w-4 h-4 accent-amber-600 rounded focus:ring-amber-500 cursor-pointer">
                  </label>
                `);
              }
            </script>
          </div>
        </div>
      </aside>

      <!-- Zone Principale : Nazareth & Illustration de Saint-Joseph -->
      <main class="flex-grow space-y-8">
        
        <section class="bg-card bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 transition-colors duration-500">
          
          <!-- Titre simplifié -->
          <h2 class="font-lora-bold text-2xl md:text-4xl text-slate-900 text-royal mb-8 text-center tracking-tight">
            Nazareth
          </h2>

          <!-- Photo Classique Peinture Saint-Joseph & Halo Réactif au survol / Clic interactif -->
          <div class="halo-container max-w-sm mx-auto mb-6 cursor-pointer flex flex-col items-center" onclick="toggleInteractiveMenu()">
            <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-slate-900">
              <img 
                src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" 
                alt="Saint-Joseph et l'Enfant-Jésus" 
                class="w-full h-auto max-h-96 object-cover rounded-xl transition-transform duration-500"
              />
            </div>
            
            <p class="text-[11px] text-slate-400 mt-3 italic text-center">
              Source : Object Lesson: St. Joseph and the Christ Child — NOMA
            </p>
          </div>

          <!-- Panneau Interactif masqué au départ (apparaît au clic sur l'image) -->
          <div id="interactive-panel" class="hidden mt-8 pt-6 border-t border-slate-100 transition-all duration-300">
            <h3 class="font-lora-bold text-xl text-center text-slate-900 text-royal mb-6">
              Saint-Joseph
            </h3>

            <!-- 3 Menus Déroulants des Titres de Saint-Joseph -->
            <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
              
              <!-- Menu 1 : Saint-Joseph le juste -->
              <div>
                <label class="block text-xs font-semibold text-slate-500 uppercase tracking-wider mb-2">Titre 1</label>
                <select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none">
                  <option value="" disabled selected>Saint-Joseph le juste</option>
                  <option value="meditation_juste">Méditation sur la justice</option>
                  <option value="priere_juste">Prière à Saint-Joseph le juste</option>
                </select>
              </div>

              <!-- Menu 2 : Saint-Joseph travailleur -->
              <div>
                <label class="block text-xs font-semibold text-slate-500 uppercase tracking-wider mb-2">Titre 2</label>
                <select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none">
                  <option value="" disabled selected>Saint-Joseph travailleur</option>
                  <option value="meditation_travail">Méditation pour les travailleurs</option>
                  <option value="priere_travail">Prière du 1er Mai</option>
                </select>
              </div>

              <!-- Menu 3 : Saint-Joseph terreur des démons -->
              <div>
                <label class="block text-xs font-semibold text-slate-500 uppercase tracking-wider mb-2">Titre 3</label>
                <select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none">
                  <option value="" disabled selected>Saint-Joseph terreur des démons</option>
                  <option value="protection">Prière de protection spirituelle</option>
                  <option value="litanie">Litanies de Saint-Joseph</option>
                </select>
              </div>

            </div>
          </div>

        </section>

      </main>

    </div>

    <!-- Pied de Page Épuré (Argent & Blanc) -->
    <footer class="text-center py-6 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
      Sous le manteau de Saint-Joseph
    </footer>

  </div>

  <!-- Audio API (Ambiance Colombe 🕊️) & Interactivité -->
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
      document.getElementById('dove-btn').classList.add('bg-amber-600', 'text-white', 'ring-2', 'ring-amber-300');
      document.getElementById('dove-status').textContent = 'Actif';

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
      document.getElementById('dove-btn').classList.remove('bg-amber-600', 'text-white', 'ring-2', 'ring-amber-300');
      document.getElementById('dove-status').textContent = 'Ambiance';
    }

    function toggleSoothingLight() {
      document.body.classList.toggle('soothing-mode');
    }

    function toggleInteractiveMenu() {
      const panel = document.getElementById('interactive-panel');
      panel.classList.toggle('hidden');
    }
  </script>
</body>
</html>
