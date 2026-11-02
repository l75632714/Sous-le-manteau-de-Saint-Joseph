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
          
          <!-- Bouton Colombe / Ambiance (SVG Vectoriel Lisible) -->
          <button id="dove-btn" onclick="toggleDoveSound()" title="Ambiance de la Colombe" class="p-3 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items-center justify-center group active:scale-95">
            <svg class="w-6 h-6 text-slate-200 group-hover:text-amber-300 transition-colors" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <!-- Silhouette stylisée et lisible d'une colombe en vol -->
              <path d="M12 4.5c-2 0-3.8.8-5 2.2C5.5 5.2 3.5 4.5 1.5 5c2 2 3 4.5 3 7.5 0 3 2.5 5 5 5h1c.5 2 2 3.5 4 3.5s3.5-1.5 3.5-3.5c0-.5-.1-1-.3-1.5 2-.5 3.8-2 4.8-4C20 12 16 12 12 4.5z"/>
              <!-- Rameau d'olivier -->
              <path d="M4.5 12.5c-1-1-2.5-1.5-3.5-1"/>
            </svg>
          </button>

          <!-- Bouton Lumière Apaisante (SVG Rayons & Halo) -->
          <button id="light-btn" onclick="toggleSoothingLight()" title="Lumière apaisante" class="p-3 rounded-xl bg-slate-800/80 hover:bg-slate-700 border border-slate-600/60 transition cursor-pointer flex items
          
