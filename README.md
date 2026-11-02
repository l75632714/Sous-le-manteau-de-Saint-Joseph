<!DOCTYPE html>
<html lang="fr" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sous le manteau de Saint-Joseph</title>
    <!-- Tailwind CSS pour un design moderne et élégant -->
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Plus+Jakarta+Sans:wght@300;400;500;600&display=swap');
        
        body {
            font-family: 'Plus Jakarta Sans', sans-serif;
        }
        
        .title-font {
            font-family: 'Cinzel', serif;
        }

        /* Style Bois d'Acacia chaleureux */
        .acacia-wood {
            background-color: #59331f;
            background-image: 
                radial-gradient(ellipse at center, rgba(145, 85, 52, 0.3) 0%, rgba(40, 20, 10, 0.8) 100%),
                repeating-linear-gradient(45deg, rgba(255, 255, 255, 0.02) 0px, rgba(255, 255, 255, 0.02) 2px, transparent 2px, transparent 8px);
            border-color: #8c5333;
        }

        /* Halo lumineux doré autour de l'avatar */
        .halo-glow {
            box-shadow: 0 0 35px 8px rgba(245, 158, 11, 0.35);
        }

        /* Sanctuaire Mode Apaisant (nuit ambrée) */
        .sanctuary-mode {
            background-color: #1c1410 !important;
            color: #fde68a !important;
        }
    </style>
</head>
<body id="main-body" class="h-full bg-stone-950 text-stone-100 flex flex-col selection:bg-amber-500 selection:text-stone-950">

    <!-- En-tête de l'application -->
    <header class="acacia-wood border-b border-amber-800/40 px-6 py-4 flex items-center justify-between shadow-lg z-20">
        <div class="flex items-center space-x-3">
            <span class="text-2xl">⚜️</span>
            <div>
                <h1 class="title-font text-base md:text-lg font-bold text-amber-200 tracking-wide">Sous le manteau de Saint-Joseph</h1>
                <p class="text-[11px] text-amber-100/75 italic">Sanctuaire de prière et de recueillement</p>
            </div>
        </div>
        
        <div class="flex items-center space-x-2">
            <!-- Bouton Lumière Apaisante (Sanctuaire) -->
            <button onclick="basculerModeSanctuaire()" id="sanctuary-btn" class="bg-stone-900/60 hover:bg-stone-900 border border-amber-500/30 text-amber-300 text-xs px-3 py-1.5 rounded-xl transition shadow flex items-center space-x-1.5">
                <span>🕯️</span> <span class="hidden sm:inline">Lumière Apaisante</span>
            </button>

            <!-- Bouton Ambiance Sonore -->
            <button onclick="basculerSon()" id="sound-btn" class="bg-stone-900/60 hover:bg-stone-900 border border-amber-500/30 text-amber-300 text-xs px-3 py-1.5 rounded-xl transition shadow flex items-center space-x-1.5">
                <span>🔔</span> <span id="sound-status">Son : Off</span>
            </button>
        </div>
    </header>

    <!-- Contenu Principal -->
    <main class="flex-1 flex flex-col lg:flex-row overflow-hidden">
        
        <!-- Panneau Gauche : Neuvaine & Cartes Historiques -->
        <div class="w-full lg:w-80 acacia-wood border-r border-amber-900/30 p-5 flex flex-col space-y-5 overflow-y-auto z-10 shadow-xl">
            
            <!-- Module Neuvaine Interactive (9 jours) -->
            <div class="bg-stone-900/80 border border-amber-600/30 rounded-2xl p-4 shadow-inner">
                <div class="flex justify-between items-center mb-3">
                    <h3 class="title-font text-xs font-bold text-amber-300 uppercase tracking-wider">Neuvaine Interactive</h3>
                    <span id="neuvaine-counter" class="text-[10px] bg-amber-500/20 text-amber-300 px-2 py-0.5 rounded-full font-semibold">0 / 9 jours</span>
                </div>
                <p class="text-[11px] text-stone-300 mb-3 leading-relaxed">Cochez chaque jour votre moment de prière et d'offrande à Saint Joseph :</p>
                
                <!-- Grille des 9 jours -->
                <div id="neuvaine-grid" class="grid grid-cols-3 gap-2">
                    <button onclick="toggleJour(1)" id="j1" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J1</button>
                    <button onclick="toggleJour(2)" id="j2" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J2</button>
                    <button onclick="toggleJour(3)" id="j3" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J3</button>
                    <button onclick="toggleJour(4)" id="j4" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J4</button>
                    <button onclick="toggleJour(5)" id="j5" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J5</button>
                    <button onclick="toggleJour(6)" id="j6" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J6</button>
                    <button onclick="toggleJour(7)" id="j7" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J7</button>
                    <button onclick="toggleJour(8)" id="j8" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J8</button>
                    <button onclick="toggleJour(9)" id="j9" class="py-2 text-xs font-medium rounded-xl border border-stone-700 bg-stone-800 text-stone-300 hover:border-amber-500 transition">J9</button>
                </div>
            </div>

            <!-- Section Cartes & Archéologie de Nazareth (Libre de droits) -->
            <div class="bg-stone-900/80 border border-amber-600/30 rounded-2xl p-4 shadow-inner space-y-3">
                <h3 class="title-font text-xs font-bold text-amber-300 uppercase tracking-wider">Nazareth Historique</h3>
                <p class="text-[11px] text-stone-300 leading-relaxed">Sites archéologiques du Ier siècle sourcés (Wikimedia Commons - Domaine Public) :</p>
                
                <div class="space-y-2 text-xs">
                    <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Excavations_Nazareth_Home_with_back_rooms_200704.JPG/800px-Excavations_Nazareth_Home_with_back_rooms_200704.JPG" target="_blank" class="block p-2 rounded-xl bg-stone-800/80 hover:bg-stone-800 border border-stone-700 text-amber-200 transition">
                        🏛️ Fouilles de la Maison du Ier siècle
                    </a>
                    <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/30/IL-Nazareth-Grotte.jpg/800px-IL-Nazareth-Grotte.jpg" target="_blank" class="block p-2 rounded-xl bg-stone-800/80 hover:bg-stone-800 border border-stone-700 text-amber-200 transition">
                        ⛪ Grotte de l'Annonciation
                    </a>
                    <a href="https://upload.wikimedia.org/wikipedia/commons/thumb/8/87/Fountain_of_Mary_Nazareth_19th_century.jpg/800px-Fountain_of_Mary_Nazareth_19th_century.jpg" target="_blank" class="block p-2 rounded-xl bg-stone-800/80 hover:bg-stone-800 border border-stone-700 text-amber-200 transition">
                        💧 Fontaine de Marie (Puits historique)
                    </a>
                </div>
            </div>
        </div>

        <!-- Centre : Sanctuaire & Avatar avec Halo lumineux -->
        <div class="flex-1 bg-stone-900 flex flex-col items-center justify-center p-6 relative overflow-hidden">
            <!-- Cercles de lumière d'ambiance -->
            <div class="absolute w-96 h-96 bg-amber-500/10 rounded-full blur-3xl pointer-events-none"></div>

            <!-- Cadre de l'Avatar de Saint Joseph -->
            <div class="relative z-10 max-w-sm w-full bg-stone-900/90 border-2 border-amber-600/60 rounded-3xl p-6 shadow-2xl flex flex-col items-center text-center halo-glow">
                
                <!-- Illustration / Icône de Saint Joseph -->
                <div class="w-32 h-32 rounded-full border-4 border-amber-500/80 flex items-center justify-center text-6xl bg-gradient-to-b from-stone-800 to-stone-900 mb-4 shadow-inner relative">
                    <span id="avatar-icon">🧔‍♂️</span>
                </div>

                <h2 id="avatar-role" class="title-font text-lg font-bold text-amber-300">Saint Joseph Travailleur</h2>
                <p class="text-xs text-stone-400 mt-1 italic">Modèle de tous ceux qui travaillent</p>

                <!-- Bouton Lecture Prière du Travailleur -->
                <button onclick="ouvrirPriereTravailleur()" class="mt-5 w-full bg-amber-600 hover:bg-amber-500 text-stone-950 font-bold py-2.5 px-4 rounded-xl text-xs transition shadow flex items-center justify-center space-x-2">
                    <span>📖</span> <span>Lire la Prière du Travailleur</span>
                </button>
            </div>
        </div>

        <!-- Panneau Droit : Menu & Personnalisation -->
        <div class="w-full lg:w-80 acacia-wood border-l border-amber-900/30 p-5 flex flex-col space-y-5 overflow-y-auto z-10 shadow-xl">
            
            <div class="space-y-3">
                <h3 class="title-font text-xs font-bold text-amber-300 uppercase tracking-wider">Sélection des Titres</h3>
                <select id="menu-titres" onchange="gererSelectionMenu(this.value)" class="w-full bg-stone-900 border border-amber-600/40 text-xs text-stone-200 rounded-xl p-2.5 outline-none focus:border-amber-400">
                    <option value="style_travailleur">Saint Joseph Travailleur</option>
                    <option value="style_juste">Saint Joseph le Juste</option>
                    <option value="style_demons">Saint Joseph Terreur des démons</option>
                </select>
            </div>

            <!-- Palette d'accents bois d'acacia & vêtements -->
            <div class="bg-stone-900/80 border border-amber-600/30 rounded-2xl p-4 shadow-inner space-y-3">
                <h4 class="text-xs font-semibold text-amber-200 uppercase tracking-wide">Palette & Bois d'Acacia</h4>
                <div>
                    <label class="block text-xs text-stone-300 mb-1.5">Nuance d'accent</label>
                    <div class="grid grid-cols-3 gap-2">
                        <button onclick="changerCouleurVetur('#965a3e')" class="py-1.5 px-2 rounded-lg bg-[#965a3e] text-[10px] font-medium text-white border border-white/20 hover:scale-105 transition shadow">Acacia</button>
                        <button onclick="changerCouleurVetur('#f8fafc')" class="py-1.5 px-2 rounded-lg bg-[#f8fafc] text-[10px] font-medium text-stone-900 border border-stone-400 hover:scale-105 transition shadow">Blanc</button>
                        <button onclick="changerCouleurVetur('#d97706')" class="py-1.5 px-2 rounded-lg bg-[#d97706] text-[10px] font-medium text-stone-950 border border-white/20 hover:scale-105 transition shadow">Doré</button>
                    </div>
                </div>
            </div>

            <!-- Zone de message d'état -->
            <div id="status-box" class="mt-auto bg-stone-900 border border-stone-700 rounded-xl p-3 text-xs text-amber-400/90">
                Application prête. Bois d'acacia et carillons chargés.
            </div>
        </div>

    </main>

    <!-- Modal Prière à Saint Joseph Travailleur -->
    <div id="prayer-modal" class="fixed inset-0 bg-stone-950/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
        <div class="bg-stone-900 border-2 border-amber-600/60 rounded-3xl p-6 max-w-md w-full shadow-2xl relative max-h-[90vh] flex flex-col">
            <div class="flex justify-between items-center mb-4 border-b border-stone-800 pb-3">
                <h3 class="title-font text-xs font-bold text-amber-400 uppercase tracking-wider">Prière à Saint Joseph Travailleur</h3>
                <button onclick="fermerPriereTravailleur()" class="text-stone-400 hover:text-stone-100 font-bold text-lg px-2">×</button>
            </div>
            <div class="overflow-y-auto flex-1 text-xs text-stone-300 leading-relaxed space-y-3 pr-2">
                <p class="font-semibold text-amber-300">Par le Pape Saint Pie X</p>
                <p>Glorieux saint Joseph, modèle de tous ceux qui sont voués au travail, obtenez-moi la grâce de travailler en esprit de pénitence pour l'expiation de mes nombreux péchés ;</p>
                <p>de travailler en conscience, mettant le culte du devoir au-dessus de mes inclinations ;</p>
                <p>de travailler avec reconnaissance et joie, regardant comme un honneur d'employer et de développer par le travail les dons reçus de Dieu ;</p>
                <p>de travailler avec ordre, paix, modération et patience, ne reculant jamais devant la lassitude et les difficultés ;</p>
                <p>de travailler surtout avec pureté d'intention et avec détachement de moi-même, ayant sans cesse devant les yeux la mort et le compte que je devrai rendre du temps perdu, des talents inutilisés, du bien omis et du mal vaniteux dans le succès, si funeste à l'œuvre de Dieu !</p>
                <p class="font-medium text-amber-200 pt-2">Tout pour Jésus, tout par Marie, tout à votre imitation, ô patriarche Joseph ! Telle sera ma devise à la vie et à la mort.</p>
                <p class="text-center font-bold text-amber-400 pt-2">Ainsi soit-il.</p>
            </div>
            <div class="mt-4 pt-3 border-t border-stone-800 flex justify-end">
                <button onclick="fermerPriereTravailleur()" class="bg-amber-600 hover:bg-amber-500 text-stone-950 font-bold py-2 px-4 rounded-xl text-xs transition">Fermer</button>
            </div>
        </div>
    </div>

    <!-- Script JavaScript interactif -->
    <script>
        let isSanctuaryActive = false;
        let isSoundActive = false;
        let audioCtx = null;
        let soundInterval = null;
        let joursCoches = JSON.parse(localStorage.getItem('neuvaine_joseph') || "[]");

        // Initialisation de la neuvaine au chargement
        document.addEventListener('DOMContentLoaded', () => {
            mettreAJourAffichageNeuvaine();
        });

        function basculerModeSanctuaire() {
            isSanctuaryActive = !isSanctuaryActive;
            const body = document.getElementById('main-body');
            const btn = document.getElementById('sanctuary-btn');
            if (isSanctuaryActive) {
                body.classList.add('sanctuary-mode');
                btn.classList.add('bg-amber-500/20', 'border-amber-400');
                document.getElementById('status-box').innerText = "Mode Lumière Apaisante activé.";
            } else {
                body.classList.remove('sanctuary-mode');
                btn.classList.remove('bg-amber-500/20', 'border-amber-400');
                document.getElementById('status-box').innerText = "Mode normal rétabli.";
            }
        }

        function toggleJour(num) {
            const index = joursCoches.indexOf(num);
            if (index > -1) {
                joursCoches.splice(index, 1);
            } else {
                joursCoches.push(num);
            }
            localStorage.setItem('neuvaine_joseph', JSON.stringify(joursCoches));
            mettreAJourAffichageNeuvaine();
        }

        function mettreAJourAffichageNeuvaine() {
            for (let i = 1; i <= 9; i++) {
                const btn = document.getElementById(`j${i}`);
                if (joursCoches.includes(i)) {
                    btn.classList.add('bg-amber-600', 'text-stone-950', 'border-amber-400', 'font-bold');
                    btn.classList.remove('bg-stone-800', 'text-stone-300');
                } else {
                    btn.classList.remove('bg-amber-600', 'text-stone-950', 'border-amber-400', 'font-bold');
                    btn.classList.add('bg-stone-800', 'text-stone-300');
                }
            }
            document.getElementById('neuvaine-counter').innerText = `${joursCoches.length} / 9 jours`;
        }

        function basculerSon() {
            isSoundActive = !isSoundActive;
            const statusText = document.getElementById('sound-status');
            const btn = document.getElementById('sound-btn');
            
            if (isSoundActive) {
                statusText.innerText = "Son : On";
                btn.classList.add('bg-amber-500/20', 'border-amber-400');
                demarrerCarillons();
            } else {
                statusText.innerText = "Son : Off";
                btn.classList.remove('bg-amber-500/20', 'border-amber-400');
                arreterCarillons();
            }
        }

        function demarrerCarillons() {
            try {
                audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                jouerCarillonCeleste();
                soundInterval = setInterval(jouerCarillonCeleste, 7000);
            } catch(e) {
                console.error("Audio non supporté");
            }
        }

        function arreterCarillons() {
            if (soundInterval) clearInterval(soundInterval);
            if (audioCtx) audioCtx.close();
        }

        function jouerCarillonCeleste() {
            if (!audioCtx || !isSoundActive) return;
            const notes = [523.25, 659.25, 783.99, 1046.50]; // Notes apaisantes
            const freq = notes[Math.floor(Math.random() * notes.length)];
            
            const osc = audioCtx.createOscillator();
            const gain = audioCtx.createGain();
            
            osc.type = 'sine';
            osc.frequency.setValueAtTime(freq, audioCtx.currentTime);
            
            gain.gain.setValueAtTime(0.01, audioCtx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.15, audioCtx.currentTime + 0.5);
            gain.gain.exponentialRampToValueAtTime(0.0001, audioCtx.currentTime + 4.0);
            
            osc.connect(gain);
            gain.connect(audioCtx.destination);
            
            osc.start();
            osc.stop(audioCtx.currentTime + 4.0);
        }

        function gererSelectionMenu(valeur) {
            const statusBox = document.getElementById('status-box');
            const role = document.getElementById('avatar-role');
            switch(valeur) {
                case 'style_juste':
                    role.innerText = 'Saint Joseph le Juste';
                    statusBox.innerText = "Mode Saint Joseph le Juste.";
                    break;
                case 'style_travailleur':
                    role.innerText = 'Saint Joseph Travailleur';
                    statusBox.innerText = "Mode Saint Joseph Travailleur.";
                    ouvrirPriereTravailleur();
                    break;
                case 'style_demons':
                    role.innerText = 'Saint Joseph Terreur des démons';
                    statusBox.innerText = "Mode Saint Joseph Terreur des démons.";
                    break;
            }
        }

        function changerCouleurVetur(couleur) {
            document.getElementById('status-box').innerText = `Nuance d'accent appliquée : ${couleur}`;
        }

        function ouvrirPriereTravailleur() {
            document.getElementById('prayer-modal').classList.remove('hidden');
        }

        function fermerPriereTravailleur() {
            document.getElementById('prayer-modal').classList.add('hidden');
        }
    </script>
</body>
</html>
