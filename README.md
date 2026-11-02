<!DOCTYPE html>
<html lang="fr" class="h-full bg-slate-50">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
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
      -webkit-tap-highlight-color: transparent;
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

        <!-- Controls Header centrés (SVG vectoriels natifs Android) -->
        <div class="flex items-center justify-center gap-3">
          
          <!-- Bouton Musique / Note -->
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance Musicale" class="p-3 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group active:scale-95">
            <svg class="w-6 h-6 text-slate-200 group-hover:text-amber-300 transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M9 18V5l12-2v13" />
              <circle cx="6" cy="18" r="3" fill="currentColor" />
              <circle cx="18" cy="16" r="3" fill="currentColor" />
            </svg>
          </button>

          <!-- Bouton Lumière Apaisante -->
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-3 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group active:scale-95">
            <svg class="w-6 h-6 text-slate-200 group-hover:text-amber-300 transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="4"/>
              <path d="M12 2v2"/>
              <path d="M12 20v2"/>
              <path d="m4.93 4.93 1.41 1.41"/>
              <path d="m17.66 17.66 1.41 1.41"/>
              <path d="M2 12h2"/>
              <path d="M20 12h2"/>
              <path d="m6.34 17.66-1.41 1.41"/>
              <path d="m19.07 4.93-1.41 1.41"/>
            </svg>
          </button>

        </div>
      </div>
    </header>

    <!-- Layout Principal : Menu Neuvaine à gauche (verrouillé), Contenu à droite -->
    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8 items-stretch">
      
      <!-- Panneau Latéral Gauche : Neuvaine (Verrouillé) -->
      <aside class="w-full md:w-72 flex-shrink-0 flex flex-col">
        <div id="neuvaine-panel" class="bg-card bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 sticky top-28 transition-colors duration-500 h-full flex flex-col justify-between">
          <div>
            <!-- Titre & Description parfaitement centrés -->
            <div class="mb-6 border-b border-slate-100 pb-4 flex flex-col items-center text-center">
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
        </div>
      </aside>

      <!-- Zone Principale : Saint Joseph -->
      <main class="flex-grow w-full flex flex-col">
        
        <section id="main-section" class="bg-card bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 transition-colors duration-500 relative flex flex-col justify-between h-full">
          
          <div class="flex flex-col h-full justify-between">
            <!-- Titre centré -->
            <div class="flex flex-col items-center">
              <h2 class="font-opensans-bold text-2xl md:text-4xl text-slate-900 text-royal mb-4 tracking-tight text-center">
                Saint Joseph
              </h2>
            </div>

            <!-- Conteneur de l'image -->
            <div class="halo-container max-w-md mx-auto relative flex flex-col items-center w-full flex-grow justify-center">
              
              <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-slate-900 w-full flex justify-center h-full max-h-[580px]">
                <img 
                  src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" 
                  alt="Saint-Joseph et l'Enfant-Jésus" 
                  class="w-full h-full object-cover rounded-xl transition-transform duration-500"
                />

                <!-- Pastille interactive 1 (Jaune pure, sans émoji et sans contour) -->
                <button onclick="openModal('dates')" title="Dates de l'année" class="absolute top-1/4 left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-amber-500 hover:bg-amber-400 shadow-lg animate-pulse transition hover:scale-110 group active:scale-95">
                  <span class="absolute bottom-full mb-1 hidden group-hover:block bg-slate-900 text-white text-[10px] px-2 py-0.5 rounded shadow whitespace-nowrap">Dates & Prières</span>
                </button>

                <!-- Pastille interactive 2 (Bleue pure, sans émoji et sans contour) -->
                <button onclick="openModal('titles')" title="Titres de Saint-Joseph" class="absolute top-1/3 right-1/4 transform translate-x-1/2 -translate-y-1/2 w-7 h-7 rounded-full bg-blue-600 hover:bg-blue-500 shadow-lg animate-pulse transition hover:scale-110 group active:scale-95">
                  <span class="absolute bottom-full mb-1 hidden group-hover:block bg-slate-900 text-white text-[10px] px-2 py-0.5 rounded shadow whitespace-nowrap">Titres de Saint-Joseph</span>
                </button>
              </div>
              
              <p class="text-[11px] text-slate-400 mt-2 italic text-center">
                Source : Object Lesson: St. Joseph and the Christ Child — NOMA
              </p>
            </div>
          </div>

          <!-- Modale / Panneau Superposé au clic sur les pastilles -->
          <div id="interactive-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-slate-950/60 backdrop-blur-sm p-4">
            <div class="bg-white rounded-2xl max-w-2xl w-full p-6 md:p-8 shadow-2xl border border-amber-200 relative animate-in fade-in zoom-in duration-200 max-h-[90vh] overflow-y-auto">
              
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

    <!-- Pied de Page Épuré - Centré -->
    <footer class="w-full text-center py-6 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
      <small>&copy; 2026 Sous le manteau de Saint Joseph. Tous droits réservés.</small>
    </footer>

  </div>

  <!-- Audio API -->
  <script>
    let audioCtx = null;
    let isPlayingDove = false;
    let melodyInterval = null;

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

      playPureNote();
      melodyInterval = setInterval(() => {
        if (isPlayingDove) {
          playPureNote();
        }
      }, 4000);
    }

    function playPureNote() {
      if (!audioCtx || !isPlayingDove) return;

      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();

      const notes = [523.25, 659.25, 783.99, 880.00, 1046.50];
      const randomFreq = notes[Math.floor(Math.random() * notes.length)];

      osc.type = 'sine';
      const now = audioCtx.currentTime;
      
      osc.frequency.setValueAtTime(randomFreq, now);

      gain.gain.setValueAtTime(0.001, now);
      gain.gain.linearRampToValueAtTime(0.03, now + 0.3);
      gain.gain.exponentialRampToValueAtTime(0.0001, now + 3.0);

      osc.connect(gain);
      gain.connect(audioCtx.destination);

      osc.start(now);
      osc.stop(now + 3.0);
    }

    function stopDoveSound() {
      isPlayingDove = false;
      if (melodyInterval) {
        clearInterval(melodyInterval);
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
          <div class="space-y-3">
            <div class="w-full p-4 rounded-xl bg-slate-50 border border-slate-200/80 flex flex-col gap-1">
              <span class="text-xs font-bold text-amber-600 uppercase">19 Mars</span>
              <button onclick="showPrayer('ave-joseph')" class="text-left text-sm font-semibold text-slate-800 hover:text-amber-700 underline transition cursor-pointer">
                Saint-Joseph, époux de la bienheureuse Vierge Marie
              </button>
            </div>
            <div class="w-full p-4 rounded-xl bg-slate-50 border border-slate-200/80 flex flex-col gap-1">
              <span class="text-xs font-bold text-amber-600 uppercase">1er Mai</span>
              <button onclick="showPrayer('pie-x')" class="text-left text-sm font-semibold text-slate-800 hover:text-amber-700 underline transition cursor-pointer">
                Saint-Joseph travailleur
              </button>
            </div>
          </div>
        `;
      } else if (type === 'titles') {
        content.innerHTML = `
          <div class="flex flex-col items-center justify-center text-center space-y-2 py-4">
            <p class="text-base font-semibold text-slate-800 w-full text-center">Le Juste,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-center">Travailleur,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-center">Terreur des démons,</p>
            <p class="text-base font-semibold text-slate-800 w-full text-center">Protecteur de la Sainte Église.</p>
          </div>
        `;
      }
      
      modal.classList.remove('hidden');
    }

    function showPrayer(prayerKey) {
      const content = document.getElementById('modal-content');
      
      if (prayerKey === 'ave-joseph') {
        content.innerHTML = `
          <div class="flex items-center justify-between mb-4 border-b pb-2 border-slate-100">
            <button onclick="openModal('dates
            
