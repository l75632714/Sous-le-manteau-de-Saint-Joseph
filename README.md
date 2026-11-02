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
    .halo-container:hover .
    leur</option>
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
