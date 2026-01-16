<!doctype html>
<html lang="hu" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Lélek_Moon</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600;700&amp;family=Quicksand:wght@300;400;500&amp;display=swap" rel="stylesheet">
  <style>
    body {
      box-sizing: border-box;
    }
    .font-mystical {
      font-family: 'Cormorant Garamond', serif;
    }
    .font-soft {
      font-family: 'Quicksand', sans-serif;
    }
    @keyframes float {
      0%, 100% { transform: translateY(0px) rotate(0deg); }
      50% { transform: translateY(-10px) rotate(2deg); }
    }
    @keyframes twinkle {
      0%, 100% { opacity: 0.3; }
      50% { opacity: 1; }
    }
    @keyframes pulse-glow {
      0%, 100% { box-shadow: 0 0 20px rgba(167, 139, 250, 0.3); }
      50% { box-shadow: 0 0 40px rgba(167, 139, 250, 0.6); }
    }
    @keyframes moon-glow {
      0%, 100% { filter: drop-shadow(0 0 10px rgba(251, 207, 232, 0.5)); }
      50% { filter: drop-shadow(0 0 25px rgba(251, 207, 232, 0.8)); }
    }
    .animate-float {
      animation: float 6s ease-in-out infinite;
    }
    .animate-twinkle {
      animation: twinkle 2s ease-in-out infinite;
    }
    .animate-pulse-glow {
      animation: pulse-glow 3s ease-in-out infinite;
    }
    .animate-moon-glow {
      animation: moon-glow 4s ease-in-out infinite;
    }
    .card-flip {
      perspective: 1000px;
    }
    .card-inner {
      transition: transform 0.8s;
      transform-style: preserve-3d;
    }
    .card-flip.flipped .card-inner {
      transform: rotateY(180deg);
    }
    .card-front, .card-back {
      backface-visibility: hidden;
    }
    .card-back {
      transform: rotateY(180deg);
    }
    .star {
      position: absolute;
      width: 4px;
      height: 4px;
      background: white;
      border-radius: 50%;
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 </head>
 <body class="h-full font-soft">
  <div id="app-wrapper" class="h-full w-full overflow-auto relative" style="background: linear-gradient(135deg, #1a1025 0%, #2d1b4e 30%, #1a1025 60%, #2d1b4e 100%);"><!-- Stars Background -->
   <div id="stars" class="fixed inset-0 pointer-events-none overflow-hidden"></div><!-- Navigation -->
   <nav class="relative z-10 px-6 py-4">
    <div class="max-w-6xl mx-auto flex items-center justify-between">
     <div class="flex items-center gap-3">
      <svg class="w-10 h-10 animate-moon-glow" viewbox="0 0 40 40" fill="none"><circle cx="20" cy="20" r="15" fill="url(#moonGrad)" /> <circle cx="25" cy="15" r="3" fill="rgba(255,255,255,0.2)" /> <circle cx="18" cy="22" r="2" fill="rgba(255,255,255,0.15)" /> <defs>
        <lineargradient id="moonGrad" x1="0%" y1="0%" x2="100%" y2="100%">
         <stop offset="0%" stop-color="#fce7f3" />
         <stop offset="100%" stop-color="#c4b5fd" />
        </lineargradient>
       </defs>
      </svg><span id="nav-title" class="font-mystical text-2xl font-semibold text-purple-200">Lélek_Moon</span>
     </div>
     <div class="hidden md:flex items-center gap-8"><a href="#cards" class="text-purple-300 hover:text-pink-300 transition-colors">Kártyák</a> <a href="#manifest" class="text-purple-300 hover:text-pink-300 transition-colors">Manifesztáció</a> <a href="#vlog" class="text-purple-300 hover:text-pink-300 transition-colors">Vlog</a> <a href="#ebooks" class="text-purple-300 hover:text-pink-300 transition-colors">E-könyvek</a> <a href="#packages" class="text-purple-300 hover:text-pink-300 transition-colors">Csomagok</a>
     </div>
    </div>
   </nav><!-- Hero Section -->
   <section class="relative z-10 px-6 py-16 text-center">
    <div class="max-w-4xl mx-auto">
     <div class="animate-float mb-8">
      <svg class="w-32 h-32 mx-auto" viewbox="0 0 120 120" fill="none"><circle cx="60" cy="60" r="45" fill="url(#heroMoon)" class="animate-moon-glow" /> <path d="M60 15 L63 25 L73 25 L65 32 L68 42 L60 36 L52 42 L55 32 L47 25 L57 25 Z" fill="#fcd34d" opacity="0.8" /> <path d="M90 30 L92 35 L97 35 L93 39 L95 44 L90 41 L85 44 L87 39 L83 35 L88 35 Z" fill="#fcd34d" opacity="0.6" /> <path d="M30 40 L32 45 L37 45 L33 49 L35 54 L30 51 L25 54 L27 49 L23 45 L28 45 Z" fill="#fcd34d" opacity="0.6" /> <circle cx="70" cy="55" r="5" fill="rgba(255,255,255,0.2)" /> <circle cx="55" cy="70" r="3" fill="rgba(255,255,255,0.15)" /> <defs>
        <radialgradient id="heroMoon" cx="40%" cy="40%">
         <stop offset="0%" stop-color="#fdf4ff" />
         <stop offset="100%" stop-color="#a78bfa" />
        </radialgradient>
       </defs>
      </svg>
     </div>
     <h1 id="hero-title" class="font-mystical text-5xl md:text-7xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-purple-300 via-pink-300 to-purple-300 mb-6">Lélek_Moon</h1>
     <p id="hero-subtitle" class="text-xl md:text-2xl text-purple-200 mb-10 max-w-2xl mx-auto">Spirituális útmutatás a belső békéhez és a tudatos élethez</p><!-- Daily Positive Message -->
     <div class="bg-gradient-to-r from-purple-900/50 via-pink-900/30 to-purple-900/50 backdrop-blur-sm rounded-2xl p-8 border border-purple-500/30 animate-pulse-glow max-w-2xl mx-auto">
      <p class="text-purple-300 text-sm uppercase tracking-widest mb-3">✨ Mai Pozitív Üzenet ✨</p>
      <p id="daily-message" class="font-mystical text-2xl text-pink-200 italic">"A belső fényed erősebb, mint bármely külső árnyék. Ma engedélyezd magadnak, hogy ragyogj."</p>
     </div>
    </div>
   </section><!-- Daily Card Section -->
   <section id="cards" class="relative z-10 px-6 py-16">
    <div class="max-w-6xl mx-auto">
     <h2 id="card-section-title" class="font-mystical text-4xl text-center text-purple-200 mb-4">Napi Kollektív Üzenet</h2>
     <p class="text-center text-purple-400 mb-12">Kattints a kártyára az üzeneted felfedéséhez</p>
     <div class="flex flex-wrap justify-center gap-8"><!-- Card 1 -->
      <div class="card-flip w-64 h-96 cursor-pointer" onclick="this.classList.toggle('flipped')">
       <div class="card-inner relative w-full h-full">
        <div class="card-front absolute inset-0 rounded-2xl bg-gradient-to-b from-purple-800 to-indigo-900 border-2 border-purple-400/50 flex items-center justify-center shadow-2xl">
         <div class="text-center p-6">
          <svg class="w-20 h-20 mx-auto mb-4 text-purple-300" viewbox="0 0 80 80" fill="currentColor"><path d="M40 10 L45 30 L65 30 L50 45 L55 65 L40 52 L25 65 L30 45 L15 30 L35 30 Z" />
          </svg>
          <p class="font-mystical text-purple-200 text-lg">Múlt</p>
          <p class="text-purple-400 text-sm mt-2">Kattints a felfedéshez</p>
         </div>
        </div>
        <div class="card-back absolute inset-0 rounded-2xl bg-gradient-to-b from-pink-900 to-purple-900 border-2 border-pink-400/50 flex items-center justify-center shadow-2xl p-6">
         <div class="text-center">
          <p class="text-pink-300 text-sm uppercase tracking-wider mb-3">A Hold</p>
          <svg class="w-16 h-16 mx-auto mb-4" viewbox="0 0 60 60" fill="none"><circle cx="30" cy="30" r="20" fill="#fce7f3" /> <circle cx="35" cy="25" r="4" fill="rgba(168,85,247,0.3)" /> <circle cx="28" cy="35" r="3" fill="rgba(168,85,247,0.2)" />
          </svg>
          <p class="font-mystical text-pink-100 text-lg leading-relaxed">Az intuíciód vezetett idáig. Bízz a belső hangodban.</p>
         </div>
        </div>
       </div>
      </div><!-- Card 2 -->
      <div class="card-flip w-64 h-96 cursor-pointer" onclick="this.classList.toggle('flipped')">
       <div class="card-inner relative w-full h-full">
        <div class="card-front absolute inset-0 rounded-2xl bg-gradient-to-b from-purple-800 to-indigo-900 border-2 border-purple-400/50 flex items-center justify-center shadow-2xl">
         <div class="text-center p-6">
          <svg class="w-20 h-20 mx-auto mb-4 text-pink-300" viewbox="0 0 80 80" fill="none" stroke="currentColor" stroke-width="2"><circle cx="40" cy="40" r="25" /> <circle cx="40" cy="40" r="15" /> <circle cx="40" cy="40" r="5" fill="currentColor" /> <line x1="40" y1="10" x2="40" y2="5" /> <line x1="40" y1="75" x2="40" y2="70" /> <line x1="10" y1="40" x2="5" y2="40" /> <line x1="75" y1="40" x2="70" y2="40" />
          </svg>
          <p class="font-mystical text-purple-200 text-lg">Jelen</p>
          <p class="text-purple-400 text-sm mt-2">Kattints a felfedéshez</p>
         </div>
        </div>
        <div class="card-back absolute inset-0 rounded-2xl bg-gradient-to-b from-pink-900 to-purple-900 border-2 border-pink-400/50 flex items-center justify-center shadow-2xl p-6">
         <div class="text-center">
          <p class="text-pink-300 text-sm uppercase tracking-wider mb-3">A Csillag</p>
          <svg class="w-16 h-16 mx-auto mb-4" viewbox="0 0 60 60" fill="none"><path d="M30 5 L35 22 L52 22 L38 33 L43 50 L30 40 L17 50 L22 33 L8 22 L25 22 Z" fill="#fcd34d" />
          </svg>
          <p class="font-mystical text-pink-100 text-lg leading-relaxed">Remény és megújulás ideje. Engedd el a félelmeket.</p>
         </div>
        </div>
       </div>
      </div><!-- Card 3 -->
      <div class="card-flip w-64 h-96 cursor-pointer" onclick="this.classList.toggle('flipped')">
       <div class="card-inner relative w-full h-full">
        <div class="card-front absolute inset-0 rounded-2xl bg-gradient-to-b from-purple-800 to-indigo-900 border-2 border-purple-400/50 flex items-center justify-center shadow-2xl">
         <div class="text-center p-6">
          <svg class="w-20 h-20 mx-auto mb-4 text-yellow-300" viewbox="0 0 80 80" fill="currentColor"><circle cx="40" cy="40" r="20" /> <path d="M40 10 L43 20 L40 15 L37 20 Z" /> <path d="M40 70 L43 60 L40 65 L37 60 Z" /> <path d="M10 40 L20 37 L15 40 L20 43 Z" /> <path d="M70 40 L60 37 L65 40 L60 43 Z" /> <path d="M18 18 L28 25 L23 23 L25 28 Z" /> <path d="M62 62 L52 55 L57 57 L55 52 Z" /> <path d="M62 18 L52 25 L57 23 L55 28 Z" /> <path d="M18 62 L28 55 L23 57 L25 52 Z" />
          </svg>
          <p class="font-mystical text-purple-200 text-lg">Jövő</p>
          <p class="text-purple-400 text-sm mt-2">Kattints a felfedéshez</p>
         </div>
        </div>
        <div class="card-back absolute inset-0 rounded-2xl bg-gradient-to-b from-pink-900 to-purple-900 border-2 border-pink-400/50 flex items-center justify-center shadow-2xl p-6">
         <div class="text-center">
          <p class="text-pink-300 text-sm uppercase tracking-wider mb-3">A Nap</p>
          <svg class="w-16 h-16 mx-auto mb-4" viewbox="0 0 60 60" fill="none"><circle cx="30" cy="30" r="12" fill="#fcd34d" /> <g stroke="#fcd34d" stroke-width="2">
            <line x1="30" y1="5" x2="30" y2="12" />
            <line x1="30" y1="48" x2="30" y2="55" />
            <line x1="5" y1="30" x2="12" y2="30" />
            <line x1="48" y1="30" x2="55" y2="30" />
           </g>
          </svg>
          <p class="font-mystical text-pink-100 text-lg leading-relaxed">Ragyogó sikerek várnak. A pozitivitásod megteremti az utad.</p>
         </div>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Manifestation Tips -->
   <section id="manifest" class="relative z-10 px-6 py-16">
    <div class="max-w-6xl mx-auto">
     <h2 id="manifest-section-title" class="font-mystical text-4xl text-center text-purple-200 mb-12">Manifesztációs Tippek</h2>
     <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">🌙</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">Újhold Rituálé</h3>
       <p class="text-purple-300 text-sm leading-relaxed">Írd le a szándékaidat újholdkor. A hold növekedésével együtt erősödik a manifestációd energiája.</p>
      </div>
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">✨</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">369 Módszer</h3>
       <p class="text-purple-300 text-sm leading-relaxed">Írd le a célodat reggel 3x, délben 6x, este 9x. A számok erejével felerősíted a vágyaidat.</p>
      </div>
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">🔮</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">Vizualizáció</h3>
       <p class="text-purple-300 text-sm leading-relaxed">Napi 5 percet tölts el az álmaid vizualizálásával. Érezd át minden érzékeddel, mintha már megtörtént volna.</p>
      </div>
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">💫</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">Hála Napló</h3>
       <p class="text-purple-300 text-sm leading-relaxed">Minden este írj 3 dolgot, amiért hálás vagy. A hála frekvenciája vonzza a bőséget.</p>
      </div>
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">🌸</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">Affirmációk</h3>
       <p class="text-purple-300 text-sm leading-relaxed">Ismételd naponta a pozitív állításokat. "Én vagyok" kezdettel programozd át a tudatalattid.</p>
      </div>
      <div class="bg-purple-900/40 backdrop-blur-sm rounded-xl p-6 border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105">
       <div class="w-14 h-14 bg-gradient-to-br from-pink-500 to-purple-600 rounded-full flex items-center justify-center mb-4"><span class="text-2xl">🦋</span>
       </div>
       <h3 class="font-mystical text-xl text-pink-200 mb-3">Elengedés</h3>
       <p class="text-purple-300 text-sm leading-relaxed">A manifesztáció után engedd el a ragaszkodást. Bízz az univerzumban és az időzítésben.</p>
      </div>
     </div>
    </div>
   </section><!-- Daily Vlog Section -->
   <section id="vlog" class="relative z-10 px-6 py-16">
    <div class="max-w-6xl mx-auto">
     <h2 class="font-mystical text-4xl text-center text-purple-200 mb-12">Napi Vlogok</h2>
     <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div class="group cursor-pointer">
       <div class="relative aspect-video rounded-xl overflow-hidden bg-gradient-to-br from-purple-800 to-pink-900 mb-4">
        <div class="absolute inset-0 flex items-center justify-center">
         <svg class="w-24 h-24 text-white/30" viewbox="0 0 100 100" fill="currentColor"><circle cx="50" cy="50" r="45" fill="none" stroke="currentColor" stroke-width="2" /> <path d="M40 30 L70 50 L40 70 Z" />
         </svg>
        </div>
        <div class="absolute inset-0 bg-purple-600/20 group-hover:bg-purple-600/40 transition-colors flex items-center justify-center">
         <div class="w-16 h-16 bg-white/20 rounded-full flex items-center justify-center group-hover:scale-110 transition-transform">
          <svg class="w-8 h-8 text-white ml-1" fill="currentColor" viewbox="0 0 24 24"><path d="M8 5v14l11-7z" />
          </svg>
         </div>
        </div><span class="absolute bottom-2 right-2 bg-black/60 text-white text-xs px-2 py-1 rounded">12:34</span>
       </div>
       <h3 class="font-mystical text-lg text-pink-200 mb-1">🌙 Heti Kollektív Olvasat</h3>
       <p class="text-purple-400 text-sm">Mit tartogat számodra ez a hét?</p>
      </div>
      <div class="group cursor-pointer">
       <div class="relative aspect-video rounded-xl overflow-hidden bg-gradient-to-br from-indigo-800 to-purple-900 mb-4">
        <div class="absolute inset-0 flex items-center justify-center">
         <svg class="w-24 h-24 text-white/30" viewbox="0 0 100 100" fill="currentColor"><path d="M50 10 L55 35 L80 35 L60 52 L68 77 L50 62 L32 77 L40 52 L20 35 L45 35 Z" />
         </svg>
        </div>
        <div class="absolute inset-0 bg-purple-600/20 group-hover:bg-purple-600/40 transition-colors flex items-center justify-center">
         <div class="w-16 h-16 bg-white/20 rounded-full flex items-center justify-center group-hover:scale-110 transition-transform">
          <svg class="w-8 h-8 text-white ml-1" fill="currentColor" viewbox="0 0 24 24"><path d="M8 5v14l11-7z" />
          </svg>
         </div>
        </div><span class="absolute bottom-2 right-2 bg-black/60 text-white text-xs px-2 py-1 rounded">8:45</span>
       </div>
       <h3 class="font-mystical text-lg text-pink-200 mb-1">✨ Reggeli Meditáció</h3>
       <p class="text-purple-400 text-sm">Indítsd a napod tudatosan</p>
      </div>
      <div class="group cursor-pointer">
       <div class="relative aspect-video rounded-xl overflow-hidden bg-gradient-to-br from-pink-800 to-purple-900 mb-4">
        <div class="absolute inset-0 flex items-center justify-center">
         <svg class="w-24 h-24 text-white/30" viewbox="0 0 100 100" fill="none" stroke="currentColor" stroke-width="2"><circle cx="50" cy="50" r="35" /> <circle cx="50" cy="50" r="25" /> <circle cx="50" cy="50" r="15" /> <circle cx="50" cy="50" r="5" fill="currentColor" />
         </svg>
        </div>
        <div class="absolute inset-0 bg-purple-600/20 group-hover:bg-purple-600/40 transition-colors flex items-center justify-center">
         <div class="w-16 h-16 bg-white/20 rounded-full flex items-center justify-center group-hover:scale-110 transition-transform">
          <svg class="w-8 h-8 text-white ml-1" fill="currentColor" viewbox="0 0 24 24"><path d="M8 5v14l11-7z" />
          </svg>
         </div>
        </div><span class="absolute bottom-2 right-2 bg-black/60 text-white text-xs px-2 py-1 rounded">15:20</span>
       </div>
       <h3 class="font-mystical text-lg text-pink-200 mb-1">🔮 Chakra Tisztítás</h3>
       <p class="text-purple-400 text-sm">Egyensúlyozd az energiaközpontjaid</p>
      </div>
     </div>
    </div>
   </section><!-- E-books Section -->
   <section id="ebooks" class="relative z-10 px-6 py-16">
    <div class="max-w-6xl mx-auto">
     <h2 class="font-mystical text-4xl text-center text-purple-200 mb-4">Manifesztációs E-könyvek</h2>
     <p class="text-center text-purple-400 mb-12">Töltsd le a tudást és kezdd el az átalakulást</p>
     <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6"><!-- E-book 1 -->
      <div class="bg-gradient-to-b from-purple-900/50 to-pink-900/40 backdrop-blur-sm rounded-xl overflow-hidden border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105 group cursor-pointer">
       <div class="aspect-[3/4] bg-gradient-to-br from-purple-700 to-pink-600 p-6 flex flex-col justify-between">
        <div>
         <div class="text-6xl mb-4">
          🌙
         </div>
         <h3 class="font-mystical text-2xl text-white mb-2">Hold Mágia</h3>
         <p class="text-purple-100 text-sm">Manifesztálj a holdciklusokkal</p>
        </div>
        <div class="text-white text-3xl font-bold">
         8.900 Ft
        </div>
       </div>
       <div class="p-4"><button class="w-full py-2 rounded-lg bg-purple-600 hover:bg-purple-500 text-white text-sm font-medium transition-colors"> Letöltés </button>
       </div>
      </div><!-- E-book 2 -->
      <div class="bg-gradient-to-b from-purple-900/50 to-pink-900/40 backdrop-blur-sm rounded-xl overflow-hidden border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105 group cursor-pointer">
       <div class="aspect-[3/4] bg-gradient-to-br from-pink-700 to-purple-600 p-6 flex flex-col justify-between">
        <div>
         <div class="text-6xl mb-4">
          ✨
         </div>
         <h3 class="font-mystical text-2xl text-white mb-2">369 Útmutató</h3>
         <p class="text-pink-100 text-sm">A Tesla-módszer lépésről lépésre</p>
        </div>
        <div class="text-white text-3xl font-bold">
         6.500 Ft
        </div>
       </div>
       <div class="p-4"><button class="w-full py-2 rounded-lg bg-purple-600 hover:bg-purple-500 text-white text-sm font-medium transition-colors"> Letöltés </button>
       </div>
      </div><!-- E-book 3 -->
      <div class="bg-gradient-to-b from-purple-900/50 to-pink-900/40 backdrop-blur-sm rounded-xl overflow-hidden border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105 group cursor-pointer">
       <div class="aspect-[3/4] bg-gradient-to-br from-indigo-700 to-purple-600 p-6 flex flex-col justify-between">
        <div>
         <div class="text-6xl mb-4">
          🔮
         </div>
         <h3 class="font-mystical text-2xl text-white mb-2">Kristály Erő</h3>
         <p class="text-purple-100 text-sm">Kristályok a manifesztációban</p>
        </div>
        <div class="text-white text-3xl font-bold">
         7.900 Ft
        </div>
       </div>
       <div class="p-4"><button class="w-full py-2 rounded-lg bg-purple-600 hover:bg-purple-500 text-white text-sm font-medium transition-colors"> Letöltés </button>
       </div>
      </div><!-- E-book 4 -->
      <div class="bg-gradient-to-b from-purple-900/50 to-pink-900/40 backdrop-blur-sm rounded-xl overflow-hidden border border-purple-500/30 hover:border-pink-400/50 transition-all hover:scale-105 group cursor-pointer">
       <div class="aspect-[3/4] bg-gradient-to-br from-purple-600 to-pink-700 p-6 flex flex-col justify-between">
        <div>
         <div class="text-6xl mb-4">
          💫
         </div>
         <h3 class="font-mystical text-2xl text-white mb-2">Álom Napló</h3>
         <p class="text-pink-100 text-sm">90 napos manifesztációs útmutató</p>
        </div>
        <div class="text-white text-3xl font-bold">
         12.900 Ft
        </div>
       </div>
       <div class="p-4"><button class="w-full py-2 rounded-lg bg-purple-600 hover:bg-purple-500 text-white text-sm font-medium transition-colors"> Letöltés </button>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Packages Section -->
   <section id="packages" class="relative z-10 px-6 py-16">
    <div class="max-w-6xl mx-auto">
     <h2 class="font-mystical text-4xl text-center text-purple-200 mb-4">Spirituális Csomagok</h2>
     <p class="text-center text-purple-400 mb-12">Válaszd ki az utadhoz illő támogatást</p>
     <div class="grid md:grid-cols-3 gap-8"><!-- Basic Package -->
      <div class="bg-gradient-to-b from-purple-900/60 to-indigo-900/60 backdrop-blur-sm rounded-2xl p-8 border border-purple-500/30 hover:border-purple-400/60 transition-all">
       <div class="text-center mb-6"><span class="text-4xl">🌱</span>
        <h3 class="font-mystical text-2xl text-purple-200 mt-4 mb-2">Kezdő Csomag</h3>
        <p class="text-pink-300 text-3xl font-semibold">15.000 Ft</p>
       </div>
       <ul class="space-y-3 mb-8">
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>3 kártyás olvasat</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Személyre szabott üzenet</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>PDF összefoglaló</span></li>
       </ul><button class="w-full py-3 rounded-xl bg-purple-600 hover:bg-purple-500 text-white font-medium transition-colors"> Választom </button>
      </div><!-- Premium Package -->
      <div class="bg-gradient-to-b from-pink-900/60 to-purple-900/60 backdrop-blur-sm rounded-2xl p-8 border-2 border-pink-400/50 hover:border-pink-300 transition-all transform scale-105 shadow-xl shadow-pink-900/30">
       <div class="absolute -top-3 left-1/2 -translate-x-1/2"><span class="bg-gradient-to-r from-pink-500 to-purple-500 text-white text-xs px-4 py-1 rounded-full uppercase tracking-wider">Legnépszerűbb</span>
       </div>
       <div class="text-center mb-6"><span class="text-4xl">🌟</span>
        <h3 class="font-mystical text-2xl text-pink-200 mt-4 mb-2">Prémium Csomag</h3>
        <p class="text-pink-300 text-3xl font-semibold">35.000 Ft</p>
       </div>
       <ul class="space-y-3 mb-8">
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Teljes kártyaolvasat</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>30 perces konzultáció</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Személyre szabott rituálé</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>2 hetes email támogatás</span></li>
       </ul><button class="w-full py-3 rounded-xl bg-gradient-to-r from-pink-500 to-purple-500 hover:from-pink-400 hover:to-purple-400 text-white font-medium transition-all"> Választom </button>
      </div><!-- VIP Package -->
      <div class="bg-gradient-to-b from-purple-900/60 to-indigo-900/60 backdrop-blur-sm rounded-2xl p-8 border border-purple-500/30 hover:border-purple-400/60 transition-all">
       <div class="text-center mb-6"><span class="text-4xl">👑</span>
        <h3 class="font-mystical text-2xl text-purple-200 mt-4 mb-2">VIP Csomag</h3>
        <p class="text-pink-300 text-3xl font-semibold">75.000 Ft</p>
       </div>
       <ul class="space-y-3 mb-8">
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Minden a Prémiumból</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Havi 4 élő olvasat</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>Személyes asztrológia</span></li>
        <li class="flex items-center gap-3 text-purple-300"><span class="text-pink-400">✓</span> <span>VIP csoport hozzáférés</span></li>
       </ul><button class="w-full py-3 rounded-xl bg-purple-600 hover:bg-purple-500 text-white font-medium transition-colors"> Választom </button>
      </div>
     </div>
    </div>
   </section><!-- Footer -->
   <footer class="relative z-10 px-6 py-12 border-t border-purple-800/50">
    <div class="max-w-6xl mx-auto text-center">
     <div class="flex items-center justify-center gap-3 mb-6">
      <svg class="w-8 h-8" viewbox="0 0 40 40" fill="none"><circle cx="20" cy="20" r="15" fill="url(#footerMoon)" /> <defs>
        <lineargradient id="footerMoon" x1="0%" y1="0%" x2="100%" y2="100%">
         <stop offset="0%" stop-color="#fce7f3" />
         <stop offset="100%" stop-color="#c4b5fd" />
        </lineargradient>
       </defs>
      </svg><span class="font-mystical text-xl text-purple-200">Lélek_Moon</span>
     </div>
     <p class="text-purple-400 mb-6">Spirituális útmutatás szeretettel ✨</p>
     <div class="flex justify-center gap-6 mb-8"><a href="#" class="w-10 h-10 rounded-full bg-purple-800/50 flex items-center justify-center text-purple-300 hover:text-pink-300 hover:bg-purple-700/50 transition-all">
       <svg class="w-5 h-5" fill="currentColor" viewbox="0 0 24 24">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z" />
       </svg></a> <a href="#" class="w-10 h-10 rounded-full bg-purple-800/50 flex items-center justify-center text-purple-300 hover:text-pink-300 hover:bg-purple-700/50 transition-all">
       <svg class="w-5 h-5" fill="currentColor" viewbox="0 0 24 24">
        <path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z" />
       </svg></a> <a href="#" class="w-10 h-10 rounded-full bg-purple-800/50 flex items-center justify-center text-purple-300 hover:text-pink-300 hover:bg-purple-700/50 transition-all">
       <svg class="w-5 h-5" fill="currentColor" viewbox="0 0 24 24">
        <path d="M19.615 3.184c-3.604-.246-11.631-.245-15.23 0-3.897.266-4.356 2.62-4.385 8.816.029 6.185.484 8.549 4.385 8.816 3.6.245 11.626.246 15.23 0 3.897-.266 4.356-2.62 4.385-8.816-.029-6.185-.484-8.549-4.385-8.816zm-10.615 12.816v-8l8 3.993-8 4.007z" />
       </svg></a>
     </div>
     <p class="text-purple-500 text-sm">© 2024 Lélek_Moon. Minden jog fenntartva.</p>
    </div>
   </footer>
  </div>
  <script>
    const defaultConfig = {
      site_title: 'Lélek_Moon',
      hero_subtitle: 'Spirituális útmutatás a belső békéhez és a tudatos élethez',
      daily_card_title: 'Napi Kollektív Üzenet',
      manifest_title: 'Manifesztációs Tippek',
      background_color: '#1a1025',
      surface_color: '#2d1b4e',
      text_color: '#e9d5ff',
      primary_action_color: '#9333ea',
      secondary_action_color: '#ec4899',
      font_family: 'Cormorant Garamond',
      font_size: 16
    };

    // Create stars
    function createStars() {
      const starsContainer = document.getElementById('stars');
      for (let i = 0; i < 100; i++) {
        const star = document.createElement('div');
        star.className = 'star animate-twinkle';
        star.style.left = Math.random() * 100 + '%';
        star.style.top = Math.random() * 100 + '%';
        star.style.animationDelay = Math.random() * 3 + 's';
        star.style.opacity = Math.random() * 0.5 + 0.3;
        starsContainer.appendChild(star);
      }
    }
    createStars();

    async function onConfigChange(config) {
      const navTitle = document.getElementById('nav-title');
      const heroTitle = document.getElementById('hero-title');
      const heroSubtitle = document.getElementById('hero-subtitle');
      const cardSectionTitle = document.getElementById('card-section-title');
      const manifestSectionTitle = document.getElementById('manifest-section-title');
      const appWrapper = document.getElementById('app-wrapper');

      if (navTitle) navTitle.textContent = config.site_title || defaultConfig.site_title;
      if (heroTitle) heroTitle.textContent = config.site_title || defaultConfig.site_title;
      if (heroSubtitle) heroSubtitle.textContent = config.hero_subtitle || defaultConfig.hero_subtitle;
      if (cardSectionTitle) cardSectionTitle.textContent = config.daily_card_title || defaultConfig.daily_card_title;
      if (manifestSectionTitle) manifestSectionTitle.textContent = config.manifest_title || defaultConfig.manifest_title;

      const bgColor = config.background_color || defaultConfig.background_color;
      const surfaceColor = config.surface_color || defaultConfig.surface_color;
      if (appWrapper) {
        appWrapper.style.background = `linear-gradient(135deg, ${bgColor} 0%, ${surfaceColor} 30%, ${bgColor} 60%, ${surfaceColor} 100%)`;
      }

      const customFont = config.font_family || defaultConfig.font_family;
      const baseFontStack = 'serif';
      document.querySelectorAll('.font-mystical').forEach(el => {
        el.style.fontFamily = `${customFont}, ${baseFontStack}`;
      });

      const baseSize = config.font_size || defaultConfig.font_size;
      if (heroTitle) heroTitle.style.fontSize = `${baseSize * 3.5}px`;
      if (heroSubtitle) heroSubtitle.style.fontSize = `${baseSize * 1.5}px`;
      if (cardSectionTitle) cardSectionTitle.style.fontSize = `${baseSize * 2.5}px`;
      if (manifestSectionTitle) manifestSectionTitle.style.fontSize = `${baseSize * 2.5}px`;
    }

    function mapToCapabilities(config) {
      return {
        recolorables: [
          {
            get: () => config.background_color || defaultConfig.background_color,
            set: (value) => { config.background_color = value; window.elementSdk.setConfig({ background_color: value }); }
          },
          {
            get: () => config.surface_color || defaultConfig.surface_color,
            set: (value) => { config.surface_color = value; window.elementSdk.setConfig({ surface_color: value }); }
          },
          {
            get: () => config.text_color || defaultConfig.text_color,
            set: (value) => { config.text_color = value; window.elementSdk.setConfig({ text_color: value }); }
          },
          {
            get: () => config.primary_action_color || defaultConfig.primary_action_color,
            set: (value) => { config.primary_action_color = value; window.elementSdk.setConfig({ primary_action_color: value }); }
          },
          {
            get: () => config.secondary_action_color || defaultConfig.secondary_action_color,
            set: (value) => { config.secondary_action_color = value; window.elementSdk.setConfig({ secondary_action_color: value }); }
          }
        ],
        borderables: [],
        fontEditable: {
          get: () => config.font_family || defaultConfig.font_family,
          set: (value) => { config.font_family = value; window.elementSdk.setConfig({ font_family: value }); }
        },
        fontSizeable: {
          get: () => config.font_size || defaultConfig.font_size,
          set: (value) => { config.font_size = value; window.elementSdk.setConfig({ font_size: value }); }
        }
      };
    }

    function mapToEditPanelValues(config) {
      return new Map([
        ['site_title', config.site_title || defaultConfig.site_title],
        ['hero_subtitle', config.hero_subtitle || defaultConfig.hero_subtitle],
        ['daily_card_title', config.daily_card_title || defaultConfig.daily_card_title],
        ['manifest_title', config.manifest_title || defaultConfig.manifest_title]
      ]);
    }

    if (window.elementSdk) {
      window.elementSdk.init({
        defaultConfig,
        onConfigChange,
        mapToCapabilities,
        mapToEditPanelValues
      });
    }
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9bec7233c0266853',t:'MTc2ODU1NDI3NC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
