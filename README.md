<!DOCTYPE html>
<html lang="fr" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sous le manteau de Saint Joseph</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Open Sans -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
</head>
<body class="bg-[#f3eee4] text-slate-800 font-['Open_Sans'] min-h-screen flex flex-col bg-cover bg-center bg-no-repeat bg-fixed transition-colors duration-300" style="background-image: url('fond-papier.jpg');">

    <!-- En-tête -->
    <header class="bg-slate-900/90 text-white shadow-md backdrop-blur-sm sticky top-0 z-40">
        <div class="max-w-4xl mx-auto px-4 py-4 flex justify-between items-center">
            <h1 class="text-xl md:text-2xl font-bold text-amber-200">Sous le manteau de Saint Joseph</h1>
            
            <div class="flex items-center space-x-3">
                <!-- Bouton Musique / Apaisement -->
                <button onclick="toggleAudio()" id="audioBtn" class="p-2 rounded-full bg-slate-800 hover:bg-slate-700 text-amber-300 transition" title="Activer / Désactiver la musique apaisante">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"></path>
                    </svg>
                </button>
                
                <!-- Bouton Ambiance Lumineuse -->
                <button onclick="toggleNightMode()" class="p-2 rounded-full bg-slate-800 hover:bg-slate-700 text-amber-300 transition" title="Changer l'ambiance lumineuse">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"></path>
                    </svg>
                </button>
            </div>
        </div>
    </header>

    <!-- Contenu Principal -->
    <main class="flex-1 max-w-4xl w-full mx-auto p-4 md:p-6 grid grid-cols-1 md:grid-cols-3 gap-6">
        
        <!-- Colonne Gauche : Neuvaine -->
        <section class="bg-white/80 backdrop-blur-sm p-5 rounded-2xl shadow-sm border border-amber-100/50 flex flex-col">
            <h2 class="text-lg font-bold text-slate-900 mb-3 border-b border-amber-200/60 pb-2">Neuvaine à Saint Joseph</h2>
            <p class="text-xs text-slate-600 mb-4">Cochez chaque jour pour suivre votre cheminement spirituel.</p>
            
            <div class="space-y-2 flex-1">
                <!-- 9 Jours de Neuvaine -->
                <script>
                    for(let i = 1; i <= 9; i++) {
                        document.write(`
                            <label class="flex items-center space-x-3 p-2 rounded-lg hover:bg-amber-50/50 cursor-pointer transition">
                                <input type="checkbox" class="w-4 h-4 text-amber-600 rounded border-slate-300 focus:ring-amber-500">
                                <span class="text-sm font-medium text-slate-700">Jour ${i}</span>
                            </label>
                        `);
                    }
                </script>
            </div>
        </section>

        <!-- Colonne Centrale / Droite : Image interactive de Saint Joseph -->
        <section class="md:col-span-2 bg-white/80 backdrop-blur-sm p-6 rounded-2xl shadow-sm border border-amber-100/50 flex flex-col items-center text-center relative">
            <h2 class="text-xl font-semibold text-slate-900 mb-2">Prier sous son Manteau</h2>
            <p class="text-sm text-slate-600 mb-4">Cliquez sur les pastilles dorées pour découvrir les prières associées.</p>
            
            <!-- Zone d'image avec pastilles -->
            <div class="relative inline-block rounded-xl overflow-hidden shadow-md max-w-sm w-full">
                <img src="saint-joseph.jpg" alt="Saint Joseph et l'Enfant Jésus" class="w-full h-auto object-cover" onError="this.src='https://via.placeholder.com/400x500?text=Saint+Joseph'">
                
                <!-- Pastille 1 : Protection du Manteau -->
                <button onclick="openModal('Prière du Manteau', 'Très saint Joseph, étends sur moi et ma famille l\'ombre protectrice de ton manteau. Accorde-nous ta paix et veille sur nos cœurs au quotidien.')" 
                        class="absolute top-1/4 left-1/3 bg-amber-400 hover:bg-amber-300 text-slate-900 w-8 h-8 rounded-full flex items-center justify-center font-bold shadow-lg transition transform hover:scale-110" title="Protection">
                    1
                </button>
                
                <!-- Pastille 2 : Travail & Famille -->
                <button onclick="openModal('Prière pour le Travail et le Foyer', 'Glorieux Saint Joseph, modèle de tous ceux qui sont voués au travail, obtiens-moi la grâce de remplir mes devoirs dans un esprit de gratitude et de joie.')" 
                        class="absolute top-1/2 right-1/4 bg-amber-400 hover:bg-amber-300 text-slate-900 w-8 h-8 rounded-full flex items-center justify-center font-bold shadow-lg transition transform hover:scale-110" title="Travail et Foyer">
                    2
                </button>
                
                <!-- Pastille 3 : Paix intérieure -->
                <button onclick="openModal('Prière pour la Paix du Cœur', 'Saint Joseph, homme silencieux et juste, enseigne-nous la valeur du silence, de l\'écoute et de la confiance abandonnée entre les mains du Seigneur.')" 
                        class="absolute bottom-1/4 left-1/2 bg-amber-400 hover:bg-amber-300 text-slate-900 w-8 h-8 rounded-full flex items-center justify-center font-bold shadow-lg transition transform hover:scale-110" title="Paix">
                    3
                </button>
            </div>
        </section>
    </main>

    <!-- Fenêtre Modale (Popup Prières) -->
    <div id="prayerModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm hidden items-center justify-center p-4 z-50">
        <div class="bg-white rounded-2xl max-w-md w-full p-6 shadow-2xl border border-amber-100 transform transition-all">
            <h3 id="modalTitle" class="text-xl font-bold text-slate-900 mb-3 text-amber-700"></h3>
            <p id="modalText" class="text-slate-700 leading-relaxed text-sm mb-6"></p>
            <div class="flex justify-end">
                <button onclick="closeModal()" class="px-5 py-2 bg-slate-800 hover:bg-slate-700 text-white text-sm font-medium rounded-xl transition">
                    Fermer
                </button>
            </div>
        </div>
    </div>

    <!-- Pied de page -->
    <footer class="bg-slate-900/90 text-slate-400 text-center py-4 text-xs mt-auto">
        <p>© Sous le manteau de Saint Joseph — Tous droits réservés</p>
    </footer>

    <!-- Scripts Javascript -->
    <script>
        // Gestion de la fenêtre modale
        function openModal(title, text) {
            document.getElementById('modalTitle').innerText = title;
            document.getElementById('modalText').innerText = text;
            const modal = document.getElementById('prayerModal');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeModal() {
            const modal = document.getElementById('prayerModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Musique apaisante (Web Audio API sans fichier externe)
        let audioCtx = null;
        let isPlaying = false;
        let intervalId = null;

        function toggleAudio() {
            if (!isPlaying) {
                if (!audioCtx) {
                    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                }
                isPlaying = true;
                document.getElementById('audioBtn').classList.add('ring-2', 'ring-amber-400');
                
                // Joue une note douce à intervalles réguliers
                const notes = [261.63, 293.66, 329.63, 392.00, 440.00]; // Gamme pentatonique douce
                intervalId = setInterval(() => {
                    if (!isPlaying) return;
                    const osc = audioCtx.createOscillator();
                    const gain = audioCtx.createGain();
                    const freq = notes[Math.floor(Math.random() * notes.length)];
                    
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
                    gain.gain.setValueAtTime(0.01, audioCtx.currentTime);
                    gain.gain.exponentialRampToValueAtTime(0.08, audioCtx.currentTime + 1);
                    gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 4);
                    
                    osc.connect(gain);
                    gain.connect(audioCtx.destination);
                    
                    osc.start();
                    osc.stop(audioCtx.currentTime + 4);
                }, 2500);
            } else {
                isPlaying = false;
                clearInterval(intervalId);
                document.getElementById('audioBtn').classList.remove('ring-2', 'ring-amber-400');
            }
        }

        // Mode Sombre / Ambiance Lumineuse
        function toggleNightMode() {
            document.body.classList.toggle('bg-slate-950');
            document.body.classList.toggle('text-slate-100');
        }
    </script>
</body>
</html>
