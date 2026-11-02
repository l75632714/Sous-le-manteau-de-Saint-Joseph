<!DOCTYPE html>
<html lang="fr" class="h-full bg-slate-50">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sous le manteau de Saint Joseph</title>

  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Fonts: Open Sans (Normale & Grasse) -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400;1,700&display=swap" rel="stylesheet">

  <style>
    body {
      font-family: 'Open Sans', sans-serif;
    }
    .font-opensans-bold {
      font-family: 'Open Sans', sans-serif;
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
    
    <!-- En-tête Moderne Bleu Royal & Argent Épuré -->
    <header class="header-bg bg-royal-header text-white shadow-lg border-b border-slate-700/50 sticky top-0 z-50 transition-colors duration-500">
      <div class="max-w-7xl mx-auto px-6 py-4 flex flex-col items-center justify-center gap-4">
        
        <!-- Titre de l'application centré -->
        <h1 class="font-opensans-bold text-2xl md:text-3xl tracking-wide text-amber-100 text-center">
          Sous le manteau de Saint-Joseph
        </h1>

        <!-- Controls Header centrés (SVG personnalisés uniquement) -->
        <div class="flex items-center justify-center gap-3">
          
          <!-- Bouton Son / Colombe (SVG personnalisé) -->
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance de la Colombe" class="p-2.5 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group">
            <svg class="w-6 h-6 text-slate-200 group-hover:text-amber-300 transition-colors" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 3c-4.97 0-9 4.03-9 9 0 2.12.74 4.07 1.97 5.61L4.35 19.35c-.39.39-.39 1.02 0 1.41.39.39 1.02.39 1.41 0L7.38 19.2C8.8 20.32 10.34 21 12 21c4.97 0 9-4.03 9-9s-4.03-9-9-9zm0 16c-3.86 0-7-3.14-7-7s3.14-7 7-7 7 3.14 7 7-3.14 7-7 7z"/>
              <path d="M12 6.5c-3.03 0-5.5 2.47-5.5 5.5 0 .83.18 1.62.51 2.33l1.58-1.58C8.36 12.44 8.5 12.23 8.5 12c0-.83.67-1.5 1.5-1.5h.5V9.5c0-.83.67-1.5 1.5-1.5z"/>
            </svg>
          </button>

          <!-- Bouton Lumière apaisante (SVG personnalisé) -->
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-2.5 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group">
            <svg class="w-6 h-6 text-slate-200 group-hover:text-amber-300 transition-colors" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-6.364-.386l1.591-1.591M3 12h2.25m.386-6.364l1.591 1.591M12 8.25a3.75 3.75 0 100 7.5 3.75 3.75 0 000-7.5z"/>
            </svg>
          </button>

        </div>
      </div>
    </header>

    <!-- Layout Principal : Menu Neuvaine à gauche (verrouillé), Contenu à droite -->
    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8 items-start">
      
      <!-- Panneau Latéral Gauche : Neuvaine (Verrouillé) -->
      <aside class="w-full md:w-72 flex-shrink-0">
        <div id="neuvaine-panel" class="bg-card bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 sticky top-28 transition-colors duration-500">
          <div class="mb-6 text-center md:text-left border-b border-slate-100 pb-4">
            <h2 class="font-opensans-bold text-xl text-slate-900 text-royal mb-1">
              Neuvaine
            </h2>
            <p class="text-xs text-slate-500 font-medium italic">
               Suivez l'avancement de votre neuvaine.
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

      <!-- Zone Principale : Saint Joseph & Illustration alignée en hauteur -->
      <main class="flex-grow w-full">
        
        <section id="main-section" class="bg-card bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 transition-colors duration-500 relative flex flex-col justify-between">
          
          <div>
            <!-- Titre simplifié -->
            <h2 class="font-opensans-bold text-2xl md:text-4xl text-slate-900 text-royal mb-6 text-center tracking-tight">
              Saint Joseph
            </h2>

            <!-- Photo Classique Peinture Saint-Joseph & Formes Interactives repérables (hauteur harmonisée) -->
            <div class="halo-container max-w-md mx-auto mb-4 relative flex flex-col items-center">
              
              <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-slate-900 w-full flex justify-center">
                <img 
                  src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" 
                  alt="Saint-Joseph et l'Enfant-Jésus" 
                  class="w-full h-[410px] md:h-[450px] object-cover rounded-xl transition-transform duration-500"
                />

                <!-- Forme / Pastille interactive 1 (Gauche - Dates de l'année) -->
                <button onclick="openModal('dates')" title="Dates de l'année" class="absolute top-1/4 left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-9 h-9 rounded-full bg-amber-500/90 hover:bg-amber-400 text-white shadow-lg flex items-center justify-center border-2 border-white animate-pulse transition hover:scale-110 group">
                  <span class="text-xs font-bold">📅</span>
                  <span class="absolute bottom-full mb-1 hidden group-hover:block bg-slate-900 text-white text-[10px] px-2 py-0.5 rounded shadow whitespace-nowrap">Dates & Prières</span>
                </button>

                <!-- Forme / Pastille interactive 2 (Droite - Titres de Saint-Joseph) -->
                <button onclick="openModal('titles')" title="Titres de Saint-Joseph" class="absolute top-1/3 right-1/4 transform translate-x-1/2 -translate-y-1/2 w-9 h-9 rounded-full bg-blue-600/90 hover:bg-blue-500 text-white shadow-lg flex items-center justify-center border-2 border-white animate-pulse transition hover:scale-110 group">
                  <span class="text-xs font-bold">👑</span>
                  <span class="absolute bottom-full mb-1 hidden group-hover:block bg-slate-900 text-white text-[10px] px-2 py-0.5 rounded shadow whitespace-nowrap">Titres de Saint-Joseph</span>
                </button>
              </div>
              
              <p class="text-[11px] text-slate-400 mt-3 italic text-center">
                Source : Object Lesson: St. Joseph and the Christ Child — NOMA
              </p>
            </div>
          </div>

          <!-- Modale / Panneau Superposé au clic sur les pastilles (Sans menus déroulants) -->
          <div id="interactive-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-slate-950/60 backdrop-blur-sm p-4">
            <div class="bg-white rounded-2xl max-w-2xl w-full p-6 md:p-8 shadow-2xl border border-amber-200 relative animate-in fade-in zoom-in duration-200">
              
              <!-- Bouton de fermeture -->
              <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-700 p-2 rounded-lg text-lg font-bold">
                ✕
              </button>

              <h3 class="font-opensans-bold text-2xl text-center text-slate-900 mb-6">
                Saint Joseph
              </h3>

              <!-- Contenu dynamique interactif sans menus déroulants -->
              <div id="modal-content" class="space-y-4">
                <!-- Rempli dynamiquement par JS -->
              </div>

            </div>
          </div>

        </section>

      </main>

    </div>

    <!-- Pied de Page Épuré (Argent & Blanc) - Centré -->
    <footer class="w-full text-center py-6 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
      <small>&copy; 2026 Sous le manteau de Saint Joseph. Tous droits réservés.</small>
    </footer>

  </div>

  <!-- Audio API & Gestion des Modales Interactives -->
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
      document.getElementById('dove-btn').classList.add('bg-amber-600', 'ring-2', 'ring-amber-300');

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
      document.getElementById('dove-btn').classList.remove('bg-amber-600', 'ring-2', 'ring-amber-300');
    }

    function toggleSoothingLight() {
      document.body.classList.toggle('soothing-mode');
    }

    function openModal(type) {
      const modal = document.getElementById('interactive-modal');
      const content = document.getElementById('modal-content');
      
      if (type === 'dates') {
        content.innerHTML = `
          <h4 class="text-xs font-semibold text-slate-500 uppercase tracking-wider mb-4">Dates & Prières de l'année</h4>
          <div class="space-y-3">
            <button onclick="alert('Chargement de la prière du 19 Mars')" class="w-full text-left p-4 rounded-xl bg-slate-50 hover:bg-amber-50 border border-slate-200/80 transition flex items-center justify-between group">
              <div>
                <span class="block text-xs font-bold text-amber-600 uppercase mb-0.5">19 Mars</span>
                <span class="text-sm font-semibold text-slate-800 group-hover:text-amber-900">Ave Joseph & Méditation</span>
              </div>
              <span class="text-xs font-bold text-amber-600">Lire →</span>
            </button>
            <button onclick="alert('Chargement de la prière du 1er Mai')" class="w-full text-left p-4 rounded-xl bg-slate-50 hover:bg-amber-50 border border-slate-200/80 transition flex items-center justify-between group">
              <div>
                <span class="block text-xs font-bold text-amber-600 uppercase mb-0.5">1er Mai</span>
                <span class="text-sm font-semibold text-slate-800 group-hover:text-amber-900">Prière du Travailleur</span>
              </div>
              <span class="text-xs font-bold text-amber-600">Lire →</span>
            </button>
          </div>
        `;
      } else if (type === 'titles') {
        content.innerHTML = `
          <h4 class="text-xs font-semibold text-slate-500 uppercase tracking-wider mb-4">Titres de Saint-Joseph</h4>
          <div class="grid grid-cols-1 md:grid-cols-3 gap-3">
            <button onclick="alert('Saint-Joseph le juste')" class="p-4 rounded-xl bg-slate-50 hover:bg-blue-50 border border-slate-200/80 text-left transition group">
              <span class="block text-xs font-bold text-blue-600 uppercase mb-1">Juste</span>
              <span class="text-sm font-semibold text-slate-800">Saint-Joseph le juste</span>
            </button>
            <button onclick="alert('Saint-Joseph travailleur')" class="p-4 rounded-xl bg-slate-50 hover:bg-blue-50 border border-slate-200/80 text-left transition group">
              <span class="block text-xs font-bold text-blue-600 uppercase mb-1">Travail</span>
              <span class="text-sm font-semibold text-slate-800">Saint-Joseph travailleur</span>
            </button>
            <button onclick="alert('Terreur des démons')" class="p-4 rounded-xl bg-slate-50 hover:bg-blue-50 border border-slate-200/80 text-left transition group">
              <span class="block text-xs font-bold text-blue-600 uppercase mb-1">Protection</span>
              <span class="text-sm font-semibold text-slate-800">Terreur des démons</span>
            </button>
          </div>
        `;
      }
      
      modal.classList.remove('hidden');
    }

    function closeModal() {
      const modal = document.getElementById('interactive-modal');
      modal.classList.add('hidden');
    }
  </script>
</body>
</html>
