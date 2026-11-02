<!DOCTYPE html>
<html lang="fr" class="h-full bg-slate-50">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Sous le manteau de Saint-Joseph</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Lora:ital,wght@0,700;1,700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Inter', sans-serif; }
    .font-lora-bold { font-family: 'Lora', serif; font-weight: 700; }
    .soothing-mode { background-color: #0f172a !important; color: #f8fafc !important; }
    .soothing-mode .bg-card { background-color: #1e293b !important; border-color: #334155 !important; color: #f8fafc !important; }
    .soothing-mode .header-bg { background-color: #020617 !important; border-bottom-color: #1e293b !important; }
    .halo-effect { box-shadow: 0 0 15px rgba(212, 175, 55, 0.25); transition: all 0.5s ease; }
    .halo-container:hover .halo-effect { box-shadow: 0 0 35px rgba(212, 175, 55, 0.65); transform: scale(1.01); }
    .bg-royal-header { background: linear-gradient(135deg, #0b192c 0%, #1e3e62 100%); }
  </style>
</head>
<body class="h-full text-slate-800 bg-slate-50 transition-colors duration-500">
  <div id="app" class="min-h-screen flex flex-col justify-between">
    <header class="header-bg bg-royal-header text-white shadow-lg border-b border-slate-700/50 sticky top-0 z-50">
      <div class="max-w-7xl mx-auto px-6 py-4 flex flex-col items-center justify-center gap-4">
        <h1 class="font-lora-bold text-2xl md:text-3xl tracking-wide text-amber-100 text-center">
          Sous le manteau de Saint-Joseph
        </h1>
        <div class="flex flex-wrap justify-center items-center gap-3 w-full">
          <select id="feasts-select" class="bg-slate-800/80 hover:bg-slate-700 text-slate-100 text-xs md:text-sm font-medium py-2 px-3 rounded-xl border border-slate-600/60 focus:outline-none focus:ring-2 focus:ring-amber-400 cursor-pointer">
            <option value="" disabled selected>Saint-Joseph dans l'année</option>
            <option value="19mars">19 Mars — Ave Joseph</option>
            <option value="1mai">1er Mai — Prière du Travailleur</option>
          </select>
          <select id="joseph-prayers-select" class="bg-amber-600/90 hover:bg-amber-500 text-slate-900 font-semibold text-xs md:text-sm py-2 px-3 rounded-xl border border-amber-400 focus:outline-none focus:ring-2 focus:ring-amber-300 cursor-pointer">
            <option value="" disabled selected>Saint-Joseph</option>
            <option value="19mars_ave">19 Mars — Ave Joseph</option>
            <option value="1mai_travailleur">1er Mai — Prière du Travailleur</option>
          </select>
          <div id="dove-btn" onclick="toggleDoveSound()" title="Ambiance de la Colombe" class="p-2 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group">
            <svg class="w-6 h-6 transition-transform duration-300 group-hover:scale-110" viewBox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M20 55 C30 55, 45 60, 55 80 C60 65, 75 45, 90 35 C75 40, 55 45, 45 35 C40 25, 30 15, 20 20 C25 30, 25 45, 20 55 Z" fill="#f8fafc" stroke="#d4af37" stroke-width="2" stroke-linejoin="round" />
              <path d="M85 32 C88 28, 92 27, 95 28 M90 30 C91 25, 96 24, 98 26" stroke="#d4af37" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
          </div>
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-2.5 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 text-slate-100 transition flex items-center text-xs md:text-sm">
            <span>💡</span>
          </button>
        </div>
      </div>
    </header>

    <div class="max-w-7xl mx-auto px-4 md:px-6 py-8 flex-grow w-full flex flex-col md:flex-row gap-8">
      <aside class="w-full md:w-72 flex-shrink-0">
        <div class="bg-card bg-white rounded-2xl p-6 shadow-sm border border-slate-200/80 sticky top-28">
          <div class="mb-6 text-center md:text-left border-b border-slate-100 pb-4">
            <h2 class="font-lora-bold text-xl text-slate-900 text-royal mb-1">9e</h2>
            <p class="text-xs text-slate-500 font-medium italic">Cocher chaque jour de votre neuvaine.</p>
          </div>
          <div class="space-y-2.5">
            <script>
              for (let i = 1; i <= 9; i++) {
                document.write(`<label class="flex items-center justify-between p-3 rounded-xl border border-slate-100 bg-slate-50/60 hover:bg-amber-50/40 hover:border-amber-200/60 cursor-pointer transition group"><span class="text-sm font-medium text-slate-700 group-hover:text-slate-900">Jour ${i}</span><input type="checkbox" class="w-4 h-4 accent-amber-600 rounded focus:ring-amber-500 cursor-pointer"></label>`);
              }
            </script>
          </div>
        </div>
      </aside>

      <main class="flex-grow space-y-8">
        <section class="bg-card bg-white rounded-2xl p-6 md:p-10 shadow-sm border border-slate-200/80 relative">
          <h2 class="font-lora-bold text-2xl md:text-4xl text-slate-900 text-royal mb-8 text-center tracking-tight">Nazareth</h2>
          
          <div class="halo-container max-w-sm mx-auto mb-6 relative flex flex-col items-center">
            <div class="relative rounded-2xl overflow-hidden halo-effect border-2 border-amber-400/40 p-1 bg-slate-900">
              <img src="https://noma.org/wp-content/uploads/2018/01/56-63-old.jpg" alt="Saint-Joseph et l'Enfant-Jésus" class="w-full h-auto max-h-96 object-cover rounded-xl" />
              <button onclick="openModal('dates')" title="Dates & Prières de l'année" class="absolute top-1/4 left-1/4 transform -translate-x-1/2 -translate-y-1/2 w-8 h-8 rounded-full bg-amber-500/90 hover:bg-amber-400 text-white shadow-lg flex items-center justify-center border-2 border-white animate-pulse transition hover:scale-110 group">
                <span class="text-xs font-bold">📅</span>
              </button>
              <button onclick="openModal('titles')" title="Titres de Saint-Joseph" class="absolute top-1/3 right-1/4 transform translate-x-1/2 -translate-y-1/2 w-8 h-8 rounded-full bg-blue-600/90 hover:bg-blue-500 text-white shadow-lg flex items-center justify-center border-2 border-white animate-pulse transition hover:scale-110 group">
                <span class="text-xs font-bold">👑</span>
              </button>
            </div>
            <p class="text-[11px] text-slate-400 mt-3 italic text-center">Source : Object Lesson: St. Joseph and the Christ Child — NOMA</p>
          </div>

          <div id="interactive-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center bg-slate-950/60 backdrop-blur-sm p-4">
            <div class="bg-white rounded-2xl max-w-2xl w-full p-6 md:p-8 shadow-2xl border border-amber-200 relative">
              <button onclick="closeModal()" class="absolute top-4 right-4 text-slate-400 hover:text-slate-700 p-2 rounded-lg text-lg font-bold">✕</button>
              <h3 class="font-lora-bold text-2xl text-center text-slate-900 mb-6">Saint-Joseph</h3>
              <div id="modal-content" class="space-y-6"></div>
            </div>
          </div>
        </section>
      </main>
    </div>

    <footer class="text-center py-6 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
      Sous le manteau de Saint-Joseph
    </footer>
  </div>

  <script>
    let audioCtx = null, isPlayingDove = false, windGain = null, birdInterval = null;
    function initAudio() { if (!audioCtx) audioCtx = new (window.AudioContext || window.webkitAudioContext)(); }
    function toggleDoveSound() { initAudio(); isPlayingDove ? stopDoveSound() : startDoveSound(); }
    function startDoveSound() {
      if (audioCtx.state === 'suspended') audioCtx.resume();
      isPlayingDove = true;
      document.getElementById('dove-btn').classList.add('bg-amber-600', 'ring-2', 'ring-amber-300');
      const bufferSize = audioCtx.sampleRate * 2, noiseBuffer = audioCtx.createBuffer(1, bufferSize, audioCtx.sampleRate), output = noiseBuffer.getChannelData(0);
      for (let i = 0; i < bufferSize; i++) output[i] = Math.random() * 2 - 1;
      const whiteNoise = audioCtx.createBufferSource(); whiteNoise.buffer = noiseBuffer; whiteNoise.loop = true;
      const filter = audioCtx.createBiquadFilter(); filter.type = 'lowpass'; filter.frequency.value = 300;
      windGain = audioCtx.createGain(); windGain.gain.value = 0.08;
      whiteNoise.connect(filter); filter.connect(windGain); windGain.connect(audioCtx.destination); whiteNoise.start();
      birdInterval = setInterval(() => { if (isPlayingDove && Math.random() > 0.3) playSoftChirp(); }, 3500);
    }
    function playSoftChirp() {
      if (!audioCtx || !isPlayingDove) return;
      const osc = audioCtx.createOscillator(), gain = audioCtx.createGain();
      osc.type = 'sine'; const now = audioCtx.currentTime, startFreq = 2200 + Math.random() * 600;
      osc.frequency.setValueAtTime(startFreq, now);
      osc.frequency.exponentialRampToValueAtTime(startFreq + 400, now + 0.1);
      osc.frequency.exponentialRampToValueAtTime(startFreq - 200, now + 0.25);
      gain.gain.setValueAtTime(0.01, now); gain.gain.linearRampToValueAtTime(0.04, now + 0.08); gain.gain.exponentialRampToValueAtTime(0.001, now + 0.25);
      osc.connect(gain); gain.connect(audioCtx.destination); osc.start(now); osc.stop(now + 0.25);
    }
    function stopDoveSound() {
      isPlayingDove = false;
      if (windGain) windGain.gain.linearRampToValueAtTime(0.001, audioCtx.currentTime + 0.5);
      if (birdInterval) clearInterval(birdInterval);
      document.getElementById('dove-btn').classList.remove('bg-amber-600', 'ring-2', 'ring-amber-300');
    }
    function toggleSoothingLight() { document.body.classList.toggle('soothing-mode'); }
    function openModal(type) {
      const modal = document.getElementById('interactive-modal'), content = document.getElementById('modal-content');
      if (type === 'dates') {
        content.innerHTML = `<h4 class="text-sm font-semibold text-slate-500 uppercase tracking-wider mb-4">Dates & Prières de l'année</h4><div class="space-y-4"><div><label class="block text-xs font-medium text-slate-600 mb-1">19 Mars — Ave Joseph</label><select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none"><option value="" disabled selected>Sélectionner une option</option><option value="ave_joseph">Prière Ave Joseph</option></select></div><div><label class="block text-xs font-medium text-slate-600 mb-1">1er Mai — Prière du Travailleur</label><select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none"><option value="" disabled selected>Sélectionner une option</option><option value="priere_travailleur">Prière du Travailleur</option></select></div></div>`;
      } else if (type === 'titles') {
        content.innerHTML = `<h4 class="text-sm font-semibold text-slate-500 uppercase tracking-wider mb-4">Titres de Saint-Joseph</h4><div class="grid grid-cols-1 md:grid-cols-3 gap-4"><div><label class="block text-xs font-semibold text-slate-500 uppercase mb-2">Saint-Joseph le juste</label><select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none"><option value="" disabled selected>Choisir</option><option value="priere_juste">Prière</option></select></div><div><label class="block text-xs font-semibold text-slate-500 uppercase mb-2">Saint-Joseph travailleur</label><select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none"><option value="" disabled selected>Choisir</option><option value="priere_travail">Prière</option></select></div><div><label class="block text-xs font-semibold text-slate-500 uppercase mb-2">Terreur des démons</label><select class="w-full bg-slate-50 border border-slate-200 text-slate-800 text-sm rounded-xl p-3 font-medium focus:ring-2 focus:ring-amber-400 focus:outline-none"><option value="" disabled selected>Choisir</option><option value="protection">Protection</option></select></div></div>`;
      }
      modal.classList.remove('hidden');
    }
    function closeModal() { document.getElementById('interactive-modal').classList.add('hidden'); }
  </script>
</body>
</html>
