<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Édition Spéciale Anniversaire de Ruchama</title>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Dancing+Script:wght@500;600;700&family=Montserrat:wght@300;400;500;600&family=Sacramento&display=swap" rel="stylesheet">
  
  <style>
    /* ==================== STYLES GÉNÉRAUX & PALETTE ==================== */
    :root {
      --bg-dark: #030611;
      --bg-card: rgba(10, 17, 40, 0.75);
      --gold-primary: #d4af37;
      --gold-light: #f9e79f;
      --gold-glow: #ffe57f;
      --night-blue: #0b1d3a;
      --text-light: #eaeff5;
      --font-main: 'Montserrat', sans-serif;
      --font-title: 'Cinzel', serif;
      --font-script: 'Dancing Script', cursive;
      --font-letter: 'Sacramento', cursive;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: radial-gradient(ellipse at bottom, #0d1b2a 0%, #030611 100%);
      color: var(--text-light);
      font-family: var(--font-main);
      min-height: 100vh;
      overflow-x: hidden;
      line-height: 1.7;
    }

    /* ==================== ANIMATION DES LUCIOLES ==================== */
    #fireflies-container {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 0;
      overflow: hidden;
    }

    .firefly {
      position: absolute;
      width: 5px;
      height: 5px;
      background-color: var(--gold-light);
      border-radius: 50%;
      box-shadow: 0 0 10px var(--gold-primary), 0 0 20px var(--gold-glow), 0 0 30px var(--gold-glow);
      animation: floatFirefly linear infinite;
      opacity: 0.8;
    }

    @keyframes floatFirefly {
      0% {
        transform: translateY(105vh) translateX(0) scale(0.6);
        opacity: 0.1;
      }
      20% { opacity: 0.9; }
      80% { opacity: 0.8; }
      100% {
        transform: translateY(-10vh) translateX(80px) scale(1.2);
        opacity: 0;
      }
    }

    /* ==================== LAYOUT CONTAINER ==================== */
    .container {
      max-width: 950px;
      margin: 0 auto;
      padding: 30px 20px;
      position: relative;
      z-index: 1;
    }

    section {
      background: var(--bg-card);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(212, 175, 55, 0.25);
      border-radius: 20px;
      padding: 35px 30px;
      margin-bottom: 45px;
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.6), inset 0 0 15px rgba(212, 175, 55, 0.05);
      transition: border-color 0.3s ease;
    }

    section:hover {
      border-color: rgba(212, 175, 55, 0.45);
    }

    h1, h2, h3 {
      font-family: var(--font-title);
      color: var(--gold-primary);
      text-align: center;
      letter-spacing: 1px;
    }

    h2 {
      font-size: 1.7rem;
      margin-bottom: 25px;
      position: relative;
      display: inline-block;
      width: 100%;
    }

    h2::after {
      content: '';
      display: block;
      width: 80px;
      height: 2px;
      background: linear-gradient(90deg, transparent, var(--gold-primary), transparent);
      margin: 10px auto 0 auto;
    }

    .quote-end {
      font-family: var(--font-script);
      font-size: 1.5rem;
      color: var(--gold-light);
      text-align: center;
      margin-top: 25px;
      padding-top: 15px;
      border-top: 1px dashed rgba(212, 175, 55, 0.3);
    }

    /* BUTTONS */
    .btn-gold {
      background: linear-gradient(135deg, #d4af37 0%, #aa7c11 100%);
      color: #030611;
      border: none;
      padding: 13px 28px;
      font-family: var(--font-main);
      font-size: 1rem;
      font-weight: 600;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
      display: block;
      margin: 20px auto;
      box-shadow: 0 5px 20px rgba(212, 175, 55, 0.4);
    }

    .btn-gold:hover {
      transform: translateY(-3px) scale(1.03);
      box-shadow: 0 8px 25px rgba(212, 175, 55, 0.6);
      background: linear-gradient(135deg, #f9e79f 0%, #d4af37 100%);
    }

    .btn-gold:active {
      transform: translateY(-1px);
    }

    /* ==================== HEADER & MUSIQUE ==================== */
    header {
      text-align: center;
      padding: 40px 20px 20px 20px;
      margin-bottom: 30px;
    }

    .main-title {
      font-size: 2.3rem;
      font-weight: 700;
      text-shadow: 0 0 15px rgba(212, 175, 55, 0.5);
      margin-bottom: 15px;
    }

    .music-msg {
      font-size: 1.05rem;
      color: var(--gold-light);
      margin-bottom: 10px;
    }

    /* ==================== COMPTE À REBOURS ==================== */
    .countdown-section {
      text-align: center;
    }

    #countdown {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-top: 20px;
      flex-wrap: wrap;
    }

    .time-card {
      background: rgba(3, 6, 17, 0.8);
      border: 1px solid var(--gold-primary);
      border-radius: 12px;
      padding: 12px 20px;
      min-width: 85px;
      box-shadow: 0 0 10px rgba(212, 175, 55, 0.2);
    }

    .time-num {
      font-family: var(--font-title);
      font-size: 1.8rem;
      color: var(--gold-glow);
      font-weight: bold;
    }

    .time-label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: var(--text-light);
      opacity: 0.8;
    }

    .birthday-party {
      font-size: 3rem;
      animation: bounce 1s infinite alternate;
    }

    @keyframes bounce {
      from { transform: translateY(0); }
      to { transform: translateY(-10px); }
    }

    /* ==================== SECTION A : ACCUEIL ==================== */
    .hero-slogan {
      font-size: 1.25rem;
      font-style: italic;
      text-align: center;
      margin: 25px 0;
      color: #ffffff;
      line-height: 1.8;
      padding: 15px;
      background: rgba(212, 175, 55, 0.08);
      border-left: 4px solid var(--gold-primary);
      border-radius: 4px;
    }

    .hero-intro {
      text-align: center;
      font-size: 1.1rem;
      color: var(--gold-light);
    }

    /* ==================== SECTIONS B & C : BOÎTES À SOUVENIRS ==================== */
    .memory-list {
      display: none;
      margin-top: 25px;
      list-style-type: none;
      animation: fadeIn 0.6s ease-in-out forwards;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(10px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .memory-list li {
      background: rgba(255, 255, 255, 0.04);
      margin: 12px 0;
      padding: 14px 20px;
      border-left: 3px solid var(--gold-primary);
      border-radius: 0 10px 10px 0;
      transition: transform 0.2s ease, background 0.2s ease;
    }

    .memory-list li:hover {
      transform: translateX(5px);
      background: rgba(212, 175, 55, 0.1);
    }

    /* ==================== SECTION D : CARTE DES ÉTOILES ==================== */
    .map-pins {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 20px;
      margin-top: 20px;
    }

    .pin-card {
      background: rgba(11, 29, 58, 0.6);
      border: 1px dashed var(--gold-primary);
      padding: 20px;
      border-radius: 15px;
      text-align: center;
      transition: all 0.3s ease;
      position: relative;
    }

    .pin-card:hover {
      transform: translateY(-5px);
      border-style: solid;
      box-shadow: 0 8px 20px rgba(212, 175, 55, 0.25);
    }

    .pin-card .pin-icon {
      font-size: 1.5rem;
      margin-bottom: 8px;
    }

    .pin-card h4 {
      color: var(--gold-light);
      font-size: 0.95rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      margin-bottom: 6px;
    }

    .pin-card p {
      color: #ffffff;
      font-weight: 600;
      font-size: 1.1rem;
    }

    /* ==================== SECTION E : COUPONS ==================== */
    .coupons-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 22px;
      margin-top: 20px;
    }

    .coupon {
      background: linear-gradient(145deg, rgba(212, 175, 55, 0.12), rgba(3, 6, 17, 0.7));
      border: 2px dashed var(--gold-primary);
      border-radius: 16px;
      padding: 22px;
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      position: relative;
      transition: all 0.3s ease;
    }

    .coupon:hover {
      border-style: solid;
      box-shadow: 0 8px 25px rgba(212, 175, 55, 0.3);
    }

    .coupon h3 {
      font-size: 1.15rem;
      margin-bottom: 10px;
    }

    .coupon p {
      font-size: 0.92rem;
      color: #d1d5db;
      margin-bottom: 15px;
    }

    .coupon-status {
      font-size: 0.9rem;
      color: #4cd137;
      font-weight: bold;
      margin-top: 10px;
      display: none;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    /* ==================== SECTION F : QUIZ ==================== */
    .quiz-card {
      background: rgba(3, 6, 17, 0.5);
      border: 1px solid rgba(212, 175, 55, 0.2);
      border-radius: 14px;
      padding: 20px;
      margin-bottom: 20px;
    }

    .quiz-q-title {
      font-size: 1.05rem;
      font-weight: 600;
      color: var(--gold-light);
      margin-bottom: 15px;
    }

    .quiz-options {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .quiz-opt-btn {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.15);
      color: #ffffff;
      padding: 12px 16px;
      border-radius: 10px;
      text-align: left;
      cursor: pointer;
      font-family: var(--font-main);
      font-size: 0.95rem;
      transition: all 0.2s ease;
    }

    .quiz-opt-btn:hover {
      background: rgba(212, 175, 55, 0.15);
      border-color: var(--gold-primary);
    }

    .quiz-opt-btn.correct {
      background: rgba(39, 174, 96, 0.3) !important;
      border-color: #27ae60 !important;
      color: #7bed9f !important;
      font-weight: bold;
    }

    .quiz-opt-btn.wrong {
      background: rgba(231, 76, 60, 0.2) !important;
      border-color: #e74c3c !important;
    }

    /* ==================== SECTION G : FACTS ==================== */
    .facts-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(210px, 1fr));
      gap: 12px;
      margin-bottom: 25px;
    }

    .fact-item {
      background: rgba(255, 255, 255, 0.04);
      padding: 12px 15px;
      border-radius: 8px;
      font-size: 0.9rem;
      border: 1px solid rgba(212, 175, 55, 0.1);
    }

    .fact-item strong {
      color: var(--gold-primary);
    }

    .extra-facts {
      background: rgba(11, 29, 58, 0.4);
      padding: 20px;
      border-radius: 12px;
      border-left: 3px solid var(--gold-primary);
    }

    .extra-facts li {
      margin-left: 20px;
      margin-bottom: 8px;
    }

    /* ==================== SECTION H : 15 BULLES ==================== */
    .bubbles-container {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      margin: 25px 0;
    }

    .firefly-bubble {
      width: 55px;
      height: 55px;
      border-radius: 50%;
      background: radial-gradient(circle, var(--gold-glow) 0%, var(--gold-primary) 70%, #997300 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #030611;
      font-weight: bold;
      font-size: 1.1rem;
      cursor: pointer;
      box-shadow: 0 0 15px var(--gold-glow);
      transition: all 0.3s ease;
      user-select: none;
    }

    .firefly-bubble:hover {
      transform: scale(1.18);
      box-shadow: 0 0 25px var(--gold-glow);
    }

    .firefly-bubble.active {
      transform: scale(1.15);
      background: radial-gradient(circle, #ffffff 0%, var(--gold-glow) 100%);
    }

    .bubble-display-box {
      min-height: 70px;
      background: rgba(3, 6, 17, 0.7);
      border: 1px solid var(--gold-primary);
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 15px;
      text-align: center;
      font-size: 1.25rem;
      color: var(--gold-light);
      font-weight: 500;
      transition: all 0.3s ease;
    }

    /* ==================== SECTION I : LETTRE ==================== */
    .envelope-box {
      text-align: center;
    }

    .parchment-letter {
      background: #fcf4dd;
      background-image: radial-gradient(#e5d3ab 1px, transparent 0);
      background-size: 16px 16px;
      color: #2c1a04;
      padding: 40px 35px;
      border-radius: 8px;
      font-family: var(--font-letter);
      font-size: 2.2rem;
      line-height: 1.6;
      box-shadow: inset 0 0 30px rgba(160, 120, 40, 0.3), 0 10px 30px rgba(0,0,0,0.5);
      display: none;
      margin-top: 20px;
      text-align: left;
      border: 1px solid #d4b87e;
      animation: fadeIn 0.8s ease-in-out forwards;
    }

    /* ==================== SECTION J & K : VŒU & ULTIME CADEAU ==================== */
    .wish-box {
      text-align: center;
    }

    #wish-input {
      width: 100%;
      max-width: 500px;
      padding: 14px 20px;
      border-radius: 30px;
      border: 1px solid var(--gold-primary);
      background: rgba(3, 6, 17, 0.8);
      color: #ffffff;
      font-family: var(--font-main);
      font-size: 1rem;
      outline: none;
      margin-bottom: 15px;
      text-align: center;
      transition: border-color 0.3s ease;
    }

    #wish-input:focus {
      border-color: var(--gold-glow);
      box-shadow: 0 0 15px rgba(212, 175, 55, 0.4);
    }

    .cake-container {
      display: none;
      margin: 30px 0;
      animation: fadeIn 0.8s ease-in-out forwards;
    }

    .cake-emoji {
      font-size: 5rem;
      animation: candlePulse 1.5s infinite alternate;
      display: inline-block;
    }

    @keyframes candlePulse {
      0% { transform: scale(1); filter: drop-shadow(0 0 10px #ff9f43); }
      100% { transform: scale(1.1); filter: drop-shadow(0 0 25px #ffc048); }
    }

    .final-section {
      display: none;
      text-align: center;
      animation: fadeIn 1.2s ease-in-out forwards;
    }

    .final-photo-frame {
      width: 100%;
      max-width: 450px;
      height: 350px;
      margin: 25px auto;
      border: 3px solid var(--gold-primary);
      border-radius: 16px;
      overflow: hidden;
      box-shadow: 0 0 30px rgba(212, 175, 55, 0.4);
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: rgba(11, 29, 58, 0.8);
    }

    .final-caption {
      font-family: var(--font-script);
      font-size: 1.8rem;
      color: var(--gold-light);
      line-height: 1.6;
      margin: 25px 0;
      padding: 0 10px;
    }

    .the-end-title {
      font-family: var(--font-title);
      font-size: 3.5rem;
      letter-spacing: 8px;
      color: var(--gold-primary);
      margin-top: 50px;
      text-shadow: 0 0 25px var(--gold-glow);
      position: relative;
      display: inline-block;
    }

    /* RESPONSIVE */
    @media (max-width: 600px) {
      .main-title { font-size: 1.7rem; }
      h2 { font-size: 1.35rem; }
      .parchment-letter { font-size: 1.7rem; padding: 25px 20px; }
      .final-caption { font-size: 1.4rem; }
      .the-end-title { font-size: 2.5rem; }
    }
  </style>
</head>
<body>

  <!-- CONTENEUR ANIMATION LUCIOLES -->
  <div id="fireflies-container"></div>

  <!-- AUDIO (Chanson de fond: Say You Won't Let It Go) -->
  <audio id="bg-music" loop preload="auto">
    <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  </audio>

  <div class="container">

    <!-- EN-TÊTE & MUSIQUE DE FOND -->
    <header>
      <h1 class="main-title">Édition Spéciale Anniversaire de Ruchama</h1>
      <p class="music-msg">🎵 Cliquez sur ce bouton pour commencer l'expérience</p>
      <button class="btn-gold" onclick="playMusic()">Lancer la musique 🎶</button>
      
      <!-- COMPTE À REBOURS -->
      <div class="countdown-section" style="margin-top:25px;">
        <p style="font-size:0.9rem; letter-spacing:1px; color:var(--gold-light);">COMPTE À REBOURS AVANT LE GRAND JOUR</p>
        <div id="countdown"></div>
      </div>
    </header>

    <!-- SECTION A : PAGE D'ACCUEIL DYNAMIQUE -->
    <section>
      <h2>Bienvenue à toi ma Lia, en espérant que le sort te soit favorable 🧚</h2>
      <div class="hero-slogan">
        « Ta présence est un cadeau que je déballe chaque jour avec la même émotion que la toute première fois. »
      </div>
      <p class="hero-intro">
        Laisse-toi guider par la magie des lucioles à travers ces pages créées tout spécialement pour toi...
      </p>
    </section>

    <!-- SECTION B : LA BOÎTE AUX BONS SOUVENIRS -->
    <section>
      <h2>La boîte aux bons souvenirs 📦✨</h2>
      <button class="btn-gold" onclick="toggleMemories('good-memories')">Ouvrir la boîte aux bons souvenirs</button>
      <ul id="good-memories" class="memory-list">
        <li>L'époque où tu t'asseyais avec Dania et Vanorah et que je te forçais à venir t'asseoir avec nous (Ama, Keyina, Thaïcha, Darley et moi) parce que t'étais la seule avec laquelle je me sentais à l'aise à l'époque.</li>
        <li>Les fois où j'essayais de te réconcilier avec ta meilleure amie.</li>
        <li>Les fois où quand tu as un problème avec ta meilleure amie tu viens m'en parler, ces moments-là me touchent car ça prouve que tu me fais confiance suffisamment.</li>
        <li>L'époque où on jouait à des jeux pour se connaître mieux.</li>
        <li>Nos fous rires en cours cette année, assises côte-à-côte.</li>
        <li>Le jour où tu m'as dit : "Caïna m defann ou tonbe en dépression" ; cette phrase m'a beaucoup touchée, car elle m'a prouvée une bonne fois pour toutes que je compte pour toi.</li>
        <li>Ces fois où je me suis abandonnée, littéralement, parce qu'avec toi, je me sens capable de surmonter n'importe quoi.</li>
        <li>Quand on colporte des ragots.</li>
        <li>Nos discussions profondes, surtout tard le soir.</li>
        <li>Quand nous marchons à deux et que tu me tiens par le poignet.</li>
        <li>Quand tu m'accordes des câlins, bien que tu n'aimes pas trop ça.</li>
        <li>Quand je te fais des bisous sur le front, bien que je n'aime pas trop ça.</li>
        <li>Quand je te dis que je suis fière de toi, et que tu prends la poudre d'escampette, parce que ça te met mal à l'aise.</li>
      </ul>
      <p class="quote-end">« Les beaux souvenirs sont des lieux où le cœur aime revenir. »</p>
    </section>

    <!-- SECTION C : LA BOÎTE AUX MAUVAIS SOUVENIRS -->
    <section>
      <h2>La boîte aux mauvais souvenirs 🌧️</h2>
      <button class="btn-gold" onclick="toggleMemories('bad-memories')">Ouvrir la boîte aux moments sombres</button>
      <ul id="bad-memories" class="memory-list">
        <li>Les fois où je me suis sentie abandonnée par ton absence.</li>
        <li>Les fois où tu me manques tellement que je me mets à pleurer.</li>
        <li>L'époque où tout n'était pas particulièrement rose dans notre relation.</li>
        <li>L'époque où nous nous sommes éloignées (pour mieux se retrouver au final).</li>
        <li>Ces fois où tu te fâches contre moi, et que tu ne veux pas m'avouer pourquoi, et que je me mets à poireauter comme une damnée.</li>
      </ul>
      <p class="quote-end">« Il semble que tout se grave mieux dans les regards, après que les pleurs ont lavé les traces fanées des souvenirs. »</p>
    </section>

    <!-- SECTION D : LA CARTE DE NOS ÉTOILES -->
    <section>
      <h2>La carte de nos étoiles 📍✨</h2>
      <div class="map-pins">
        <div class="pin-card">
          <div class="pin-icon">📍</div>
          <h4>Première rencontre</h4>
          <p>CMA</p>
        </div>
        <div class="pin-card">
          <div class="pin-icon">💬</div>
          <h4>Première interaction</h4>
          <p>Salle de 8e I</p>
        </div>
        <div class="pin-card">
          <div class="pin-icon">🚪</div>
          <h4>Lieu d'évasion</h4>
          <p>La toilette privée</p>
        </div>
        <div class="pin-card">
          <div class="pin-icon">🏫</div>
          <h4>Le QG / Retrouvailles</h4>
          <p>La ruelle des toilettes du RDC</p>
        </div>
        <div class="pin-card">
          <div class="pin-icon">📱</div>
          <h4>Lieu des secrets</h4>
          <p>WhatsApp</p>
        </div>
      </div>
    </section>

    <!-- SECTION E : LE LIVRE DES COUPONS -->
    <section>
      <h2>Le Livre des Coupons 🎫✨</h2>
      <div class="coupons-grid">
        <div class="coupon">
          <h3>Reine de la journée 👑</h3>
          <p>Toutes tes envies (dans la limite du raisonnable) sont des ordres pendant 24h (dis-le à AMA et à AMALIE stp, ordre de Caïna).</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Concert Privé 🎤</h3>
          <p>Je t'interprète ta chanson préférée avec la plus grande ferveur sous la douche ou dans le salon.</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>"Tu avais raison" ⚖️</h3>
          <p>Un coupon à sortir lors d'un petit désaccord pour que je te donne officiellement raison sans discuter.</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Assistante Personnelle 💼</h3>
          <p>Je serai une assistante personnelle dédiée à porter tes affaires au premier jour de la rentrée des classes.</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Une Première Fois 🌟</h3>
          <p>Tester ensemble une activité que nous n'avons encore jamais faite.</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Convos Profondes 🌙</h3>
          <p>Des conversations profondes plus souvent, même si tu les évites comme la peste !</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Séance Photo Duo 📸</h3>
          <p>Une série de photos souvenirs ensemble pour toute l'année à venir.</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>

        <div class="coupon">
          <h3>Un Joker 🃏</h3>
          <p>Demande-moi n'importe quoi et je le ferai !</p>
          <button class="btn-gold" onclick="activateCoupon(this)">Activer ce coupon</button>
          <div class="coupon-status">✨ Bon activé ! ✨</div>
        </div>
      </div>
    </section>

    <!-- SECTION F : LE QUIZ DE LA LUCIOLE -->
    <section>
      <h2>Le Quiz de la Luciole 💡 Quiz Interactif</h2>
      <div id="quiz-container">
        
        <div class="quiz-card">
          <p class="quiz-q-title">1. Pourquoi es-tu ma Luciole ?</p>
          <div class="quiz-options">
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option A : Parce que tu illumines mes journées.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option B : Parce que tu es magique et unique.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, true)">Option C : Les deux, et bien plus encore ! ✨</button>
          </div>
        </div>

        <div class="quiz-card">
          <p class="quiz-q-title">2. Quel est ton plus grand super-pouvoir à mes yeux ?</p>
          <div class="quiz-options">
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option A : Ton sourire capable de réparer n'importe quelle mauvaise journée.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option B : Ta capacité à me faire rire en une fraction de seconde.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, true)">Option C : L'ensemble de tes petites magies du quotidien ! ✨</button>
          </div>
        </div>

        <div class="quiz-card">
          <p class="quiz-q-title">3. Qu'est-ce que je nous souhaite pour les années à venir ?</p>
          <div class="quiz-options">
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option A : Encore plus de voyages et de découvertes fantastiques.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option B : Des milliers d'autres fous rires complices.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, true)">Option C : Une infinité de moments magiques avec ma Luciole. ✨</button>
          </div>
        </div>

        <div class="quiz-card">
          <p class="quiz-q-title">4. Qu'est-ce qui prouve qu'on forme la meilleure équipe du monde ?</p>
          <div class="quiz-options">
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option A : On termine les phrases de l'autre sans même y penser.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option B : On se comprend juste avec un simple regard en public.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, true)">Option C : Tout ça à la fois, et le fait qu'on soit tout simplement inséparables ! ✨</button>
          </div>
        </div>

        <div class="quiz-card">
          <p class="quiz-q-title">5. Quel est le meilleur moment de la journée d'après moi ?</p>
          <div class="quiz-options">
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option A : La première gorgée de café le matin.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, false)">Option B : Le coucher de soleil en fin d'après-midi.</button>
            <button class="quiz-opt-btn" onclick="answerQuiz(this, true)">Option C : Chaque seconde partagée avec toi, peu importe l'heure ! ✨</button>
          </div>
        </div>

      </div>
    </section>

    <!-- SECTION G : FACTS ABOUT MA LUCIOLE -->
    <section>
      <h2>Facts about ma Luciole 🔍⭐</h2>
      <div class="facts-grid">
        <div class="fact-item"><strong>Name :</strong> Ruchama Lia Achille</div>
        <div class="fact-item"><strong>Age :</strong> 15</div>
        <div class="fact-item"><strong>Birthday :</strong> 08.09.2011</div>
        <div class="fact-item"><strong>Zodiac Sign :</strong> Lion ♌</div>
        <div class="fact-item"><strong>Family status :</strong> Last-born</div>
        <div class="fact-item"><strong>Religion :</strong> Christian-protestant</div>
        <div class="fact-item"><strong>Dream career :</strong> Educational Sciences & Psychologist</div>
        <div class="fact-item"><strong>Favorite colors :</strong> Black & pastel colors</div>
        <div class="fact-item"><strong>Favorite subject :</strong> Maths 📐</div>
        <div class="fact-item"><strong>Favorite sport :</strong> Football ⚽</div>
        <div class="fact-item"><strong>Favorite player :</strong> Alejandro Balde</div>
        <div class="fact-item"><strong>Favorite club :</strong> Barça 🔵🔴</div>
        <div class="fact-item"><strong>Favorite country :</strong> Argentina 🇦🇷</div>
        <div class="fact-item"><strong>Favorite slogan :</strong> Visca el Barça i visca Catalunya</div>
        <div class="fact-item"><strong>Favorite shows :</strong> Xo Kitty, You, To all the boys I've loved before, The Rookie</div>
        <div class="fact-item"><strong>Favorite animated movies :</strong> Zootopia, Raiponce, Moana</div>
        <div class="fact-item"><strong>Favorite animated series :</strong> Barbie</div>
        <div class="fact-item"><strong>Hobbies :</strong> TikTok, Series, Brazilian dances 💃</div>
        <div class="fact-item"><strong>Goal in life :</strong> Make a positive impact on everyone</div>
        <div class="fact-item"><strong>Favorite flower :</strong> Hibiscus 🌺</div>
        <div class="fact-item"><strong>Must-carry items :</strong> Perfume, gloss, money, cream</div>
      </div>

      <div class="extra-facts">
        <h4 style="color:var(--gold-light); margin-bottom:10px;">Encore plus de détails :</h4>
        <ul>
          <li>Elle aime se distinguer des autres.</li>
          <li>Elle n'a pas d'artiste préféré mais aime beaucoup James Arthur.</li>
          <li>Elle aime particulièrement Tems, surtout sa chanson <em>"Raindance"</em>.</li>
          <li>Elle n'écoute pas un genre musical spécifique mais son genre est définitivement le RnB.</li>
          <li>Elle déteste les mensonges.</li>
          <li>Elle déteste son sourire mais rigole tellement facilement !</li>
          <li>Elle aime la glace <strong>"Rum Raisin"</strong> avec une passion immense ! 🍦</li>
        </ul>
      </div>
    </section>

    <!-- SECTION H : 15 CHOSES QUE J'AIME CHEZ TOI -->
    <section>
      <h2>15 choses que j'aime chez toi 💛</h2>
      <p style="text-align:center; color:var(--gold-light);">Clique sur chaque luciole pour faire apparaître une raison :</p>
      
      <div class="bubbles-container" id="bubbles-list"></div>
      
      <div class="bubble-display-box" id="bubble-display">
        ✨ Cliquez sur un numéro ci-dessus ✨
      </div>
    </section>

    <!-- SECTION I : LETTRE DE CAÏNA -->
    <section class="envelope-box">
      <h2>La Lettre de Caïna ✉️</h2>
      <button class="btn-gold" onclick="openLetter()">Ouvrir l'enveloppe 💌</button>
      
      <div id="parchment-letter" class="parchment-letter">
        Ma chère Lia,<br><br>
        En ce jour si spécial, je tenais à poser ces mots pour te rappeler combien ta présence compte pour moi. À travers nos fous rires, nos secrets partagés et même nos moments plus difficiles, tu es et tu resteras ma petite sœur adorée, ma complice de toujours.<br><br>
        Merci d'être cette personne magnifique, drôle, loyale et unique.<br><br>
        Joyeux Anniversaire ma Luciole ! 🎂✨<br><br>
        Avec tout mon amour,<br>
        <strong>Caïna</strong>
      </div>
    </section>

    <!-- SECTION J : UN VŒU SOUS LES ÉTOILES -->
    <section class="wish-box">
      <h2>Un vœu sous les étoiles 🌟</h2>
      <p style="margin-bottom:15px;">Écris ton vœu pour cette nouvelle année :</p>
      <input type="text" id="wish-input" placeholder="Ton vœu secret ici...">
      <button class="btn-gold" onclick="makeWish()">Valider mon vœu 🌠</button>

      <div id="cake-animation" class="cake-container">
        <div class="cake-emoji">🎂✨</div>
        <p style="color:var(--gold-light); margin-top:10px;">Ton vœu a été envoyé vers les étoiles...</p>
        <button class="btn-gold" id="btn-ultimate" style="margin-top:20px;" onclick="showFinalSection()">Découvre ton ultime cadeau 🎁</button>
      </div>
    </section>

    <!-- SECTION K : ULTIME CADEAU & FINAL -->
    <section id="final-section" class="final-section">
      <h2>Ton Ultime Cadeau 🎁</h2>
      
      <!-- PHOTO DE COUVERTURE / ULTIME CADEAU -->
      <div class="final-photo-frame" style="background-image: url('photo.jpg');">
        <!-- Message de fallback si photo.jpg n'est pas encore ajoutée -->
        <div style="background: rgba(3,6,17,0.7); padding: 10px 20px; border-radius: 8px; font-size: 0.9rem;">
          📷 [ Place ta photo nommée <strong>photo.jpg</strong> dans le même dossier ]
        </div>
      </div>

      <p class="final-caption">
        « À tes côtés, j'ai appris que le bonheur ne se cherche pas, il se vit.<br>
        Tu es ma petite soeur adorée, ma complice dans chaque éclat de rire et mon soutien dans chaque silence. Je t'aime♥️ »
      </p>

      <div class="the-end-title">THE END</div>
    </section>

  </div>

  <script>
    /* 1. ANIMATION DYNAMIQUE DES LUCIOLES */
    function createFireflies() {
      const container = document.getElementById('fireflies-container');
      const count = 45;
      for (let i = 0; i < count; i++) {
        const firefly = document.createElement('div');
        firefly.className = 'firefly';
        firefly.style.left = Math.random() * 100 + 'vw';
        firefly.style.animationDuration = (Math.random() * 6 + 6) + 's';
        firefly.style.animationDelay = (Math.random() * 6) + 's';
        const size = Math.random() * 3 + 3;
        firefly.style.width = size + 'px';
        firefly.style.height = size + 'px';
        container.appendChild(firefly);
      }
    }
    createFireflies();

    /* 2. MUSIQUE DE FOND */
    function playMusic() {
      const audio = document.getElementById('bg-music');
      audio.play().then(() => {
        alert("🎵 Musique lancée ! Profite de l'expérience.");
      }).catch(err => {
        alert("Cliquez sur la page puis réessayez de lancer la musique.");
      });
    }

    /* 3. COMPTE À REBOURS (9 Août à minuit) */
    function updateCountdown() {
      const now = new Date();
      let targetYear = now.getFullYear();
      let targetDate = new Date(`August 9, ${targetYear} 00:00:00`);

      // Si le 9 août de cette année est passé et qu'on n'est pas le 9 août
      if (now > targetDate && now.getDate() !== 9) {
        targetDate = new Date(`August 9, ${targetYear + 1} 00:00:00`);
      }

      const isBirthday = (now.getDate() === 9 && now.getMonth() === 7); // Mois 7 = Août

      const cdContainer = document.getElementById('countdown');
      if (isBirthday) {
        cdContainer.innerHTML = "<div class='birthday-party'>🎊 Joyeux Anniversaire Ruchama ! 🎊</div>";
        return;
      }

      const diff = targetDate - now;
      if (diff <= 0) {
        cdContainer.innerHTML = "<div class='birthday-party'>🎊 Joyeux Anniversaire Ruchama ! 🎊</div>";
        return;
      }

      const d = Math.floor(diff / (1000 * 60 * 60 * 24));
      const h = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const m = Math.floor((diff / (1000 * 60)) % 60);
      const s = Math.floor((diff / 1000) % 60);

      cdContainer.innerHTML = `
        <div class="time-card"><div class="time-num">${d}</div><div class="time-label">Jours</div></div>
        <div class="time-card"><div class="time-num">${h}</div><div class="time-label">Heures</div></div>
        <div class="time-card"><div class="time-num">${m}</div><div class="time-label">Min</div></div>
        <div class="time-card"><div class="time-num">${s}</div><div class="time-label">Sec</div></div>
      `;
    }
    setInterval(updateCountdown, 1000);
    updateCountdown();

    /* 4. AFFICHER BONS / MAUVAIS SOUVENIRS */
    function toggleMemories(id) {
      const el = document.getElementById(id);
      if (el.style.display === 'block') {
        el.style.display = 'none';
      } else {
        el.style.display = 'block';
      }
    }

    /* 5. ACTIVATION DES COUPONS */
    function activateCoupon(btn) {
      btn.style.display = 'none';
      const status = btn.nextElementSibling;
      status.style.display = 'block';
    }

    /* 6. QUIZ INTERACTIF */
    function answerQuiz(btn, isCorrect) {
      const parent = btn.parentElement;
      const buttons = parent.querySelectorAll('.quiz-opt-btn');
      
      buttons.forEach(b => b.classList.remove('correct', 'wrong'));

      if (isCorrect) {
        btn.classList.add('correct');
        alert("✨ Bravo Lia ! C'est la réponse parfaite ! ✨");
      } else {
        btn.classList.add('wrong');
        alert("Oups ! Réessaie, ma Luciole ! 🧚");
      }
    }

    /* 7. 15 CHOSES QUE J'AIME CHEZ TOI (15 BULLES) */
    const reasons = [
      "1. Ton sourire",
      "2. Ton rire",
      "3. Tes fossettes",
      "4. Tes side eyes",
      "5. Ton grain de folie",
      "6. Ta force de caractère",
      "7. Tes câlins",
      "8. Ta voix",
      "9. Ton côté mauvaise perdante",
      "10. Ta loyauté",
      "11. Ton sens du détail",
      "12. Ton réalisme",
      "13. Ton enthousiasme",
      "14. Ta voix quand tu es grippée",
      "15. TOI"
    ];

    const bubblesContainer = document.getElementById('bubbles-list');
    const displayBox = document.getElementById('bubble-display');

    reasons.forEach((reasonText, idx) => {
      const bubble = document.createElement('div');
      bubble.className = 'firefly-bubble';
      bubble.innerText = idx + 1;
      bubble.onclick = function() {
        document.querySelectorAll('.firefly-bubble').forEach(b => b.classList.remove('active'));
        bubble.classList.add('active');
        displayBox.innerHTML = `✨ ${reasonText} ✨`;
      };
      bubblesContainer.appendChild(bubble);
    });

    /* 8. OUVERTURE DE LA LETTRE */
    function openLetter() {
      const letter = document.getElementById('parchment-letter');
      letter.style.display = 'block';
    }

    /* 9. VŒU SOUS LES ÉTOILES */
    function makeWish() {
      const input = document.getElementById('wish-input');
      if (input.value.trim() === "") {
        alert("Écris un petit vœu avant de valider ! 🌟");
        return;
      }
      document.getElementById('cake-animation').style.display = 'block';
    }

    /* 10. ULTIME CADEAU */
    function showFinalSection() {
      const finalSec = document.getElementById('final-section');
      finalSec.style.display = 'block';
      finalSec.scrollIntoView({ behavior: 'smooth' });
    }
  </script>
</body>
</html>
