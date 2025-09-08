# Web-Khusus-Danang(By LeafZuya)
<html lang="id">
<head>
  <meta name="google-site-verification" content="df6EtL6mKtOPWlg4bi57__R4cjbLIAuNwZisuD42fHo" />
  <title>Web Khusus Danang by [Leaf"Corp]LeafZuya (Daffa)</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: radial-gradient(circle at top left, rgba(255,255,200,0.4), transparent 50%),
                  linear-gradient(135deg, #87CEFA, #ffffff, #b3e5ff);
      color: #333;
      overflow-x: hidden;
      min-height: 100vh;
      position: relative;
      overflow: hidden;
    }

    header {
      text-align: center;
      padding: 50px 20px;
      color: white;
      background: linear-gradient(135deg, rgba(0,150,200,0.6), rgba(0,200,255,0.6));
      border-bottom: 4px solid #2196f3;
      position: relative;
      overflow: hidden;
    }

    header h1 {
      font-size: 2.7rem;
      margin-bottom: 12px;
      text-shadow: 2px 2px 10px rgba(0,0,0,0.4);
    }

    header p {
      font-size: 1.2rem;
      opacity: 0.95;
    }

    /* Emoji hiasan */
    .emoji-decor {
      position: absolute;
      font-size: 2rem;
      animation: float 6s infinite ease-in-out;
    }
    .emoji1 { top: 10px; left: 20px; animation-delay: 0s; }
    .emoji2 { top: 50px; right: 20px; animation-delay: 2s; }
    .emoji3 { bottom: 15px; left: 50%; transform: translateX(-50%); animation-delay: 4s; }

    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-15px); }
    }

    /* Container Card */
    .container {
      column-count: 3;
      column-gap: 25px;
      padding: 50px 20px;
      max-width: 1200px;
      margin: auto;
      position: relative;
      z-index: 2;
    }

    /* Card baru dengan efek kilauan emas dan melayang */
    .card {
      display: inline-block;
      width: 100%;
      margin: 0 0 25px;
      background: linear-gradient(135deg, #fff9e6, #fff0c2);
      border-radius: 22px;
      padding: 22px;
      border: 2px solid #ffd700;
      box-shadow: 0 10px 25px rgba(0,0,0,0.15),
                  0 0 20px rgba(255, 215, 0, 0.4),
                  inset 0 0 15px rgba(255, 215, 0, 0.2);
      transition: transform 0.4s ease, box-shadow 0.4s ease;
      text-align: center;
      position: relative;
      overflow: hidden;
      animation: floating 5s infinite ease-in-out;
    }

    /* Efek kilauan emas */
    .card::before {
      content: '';
      position: absolute;
      top: -50%;
      left: -50%;
      width: 200%;
      height: 200%;
      background: linear-gradient(
        45deg,
        rgba(255, 215, 0, 0) 0%,
        rgba(255, 215, 0, 0.1) 50%,
        rgba(255, 215, 0, 0) 100%
      );
      transform: rotate(45deg);
      animation: shine 4s infinite;
      z-index: 1;
    }

    /* Konten card di atas efek kilauan */
    .card > * {
      position: relative;
      z-index: 2;
    }

    /* Animasi melayang */
    @keyframes floating {
      0%, 100% { transform: translateY(0) rotate(0.5deg); }
      50% { transform: translateY(-10px) rotate(-0.5deg); }
    }

    /* Animasi kilauan */
    @keyframes shine {
      0% { left: -100%; }
      20% { left: 100%; }
      100% { left: 100%; }
    }

    .card:nth-child(2) {
      animation-delay: 1s;
    }

    .card:nth-child(3) {
      animation-delay: 2s;
    }

    .card:nth-child(4) {
      animation-delay: 1.5s;
    }

    .card:hover {
      transform: translateY(-15px) scale(1.05) rotate(2deg);
      box-shadow: 0 20px 40px rgba(0,0,0,0.25),
                  0 0 30px rgba(255, 215, 0, 0.6),
                  inset 0 0 20px rgba(255, 215, 0, 0.3);
      animation-play-state: paused;
    }

    .card h2 {
      font-size: 1.6rem;
      margin-bottom: 12px;
      color: #b8860b;
      text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
    }

    .card p {
      font-size: 1rem;
      color: #5a4a00;
      line-height: 1.6;
    }

    iframe {
      border-radius: 15px;
      margin: 10px;
    }

    /* Tombol */
    button {
      background: linear-gradient(135deg, #4caf50, #2196f3);
      border: none;
      padding: 12px 24px;
      border-radius: 30px;
      color: white;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
      margin-top: 10px;
    }
    button:hover {
      transform: scale(1.1);
      background: linear-gradient(135deg, #2e7d32, #1565c0);
      box-shadow: 0 8px 15px rgba(0,0,0,0.3);
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 25px;
      background: linear-gradient(135deg, rgba(0,100,180,0.6), rgba(0,70,200,0.6));
      color: white;
      margin-top: 50px;
      border-top: 4px solid #2196f3;
      font-size: 1rem;
      position: relative;
    }

    .footer-emoji {
      font-size: 1.5rem;
      margin: 0 5px;
      animation: bounce 3s infinite ease-in-out;
    }

    @keyframes bounce {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-6px); }
    }

    /* Efek bintang melayang */
    .star {
      position: absolute;
      font-size: 1.2rem;
      color: gold;
      animation: twinkle 4s infinite ease-in-out, drift 8s infinite linear;
      opacity: 0.9;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.8; transform: scale(1); }
      50% { opacity: 0.2; transform: scale(1.3); }
    }

    @keyframes drift {
      0% { transform: translateY(0) translateX(0); }
      50% { transform: translateY(-30px) translateX(20px); }
      100% { transform: translateY(0) translateX(0); }
    }
  </style>
</head>
<body>
  <header>
    <h1>🌟 Welcome to Website Khusus Danang...🌟</h1>
    <p>Dibuat oleh LeafZuya (Daffa) 😎🤭</p>

    <div class="emoji-decor emoji1">🍀</div>
    <div class="emoji-decor emoji2">✨</div>
    <div class="emoji-decor emoji3">💙</div>
  </header>

  <!-- 10 pasang bintang melayang -->
  <div class="star" style="top: 10%; left: 15%;">✨</div>
  <div class="star" style="top: 12%; left: 18%;">🌟</div>
  <div class="star" style="top: 25%; left: 40%;">✨</div>
  <div class="star" style="top: 28%; left: 43%;">🌟</div>
  <div class="star" style="top: 40%; left: 70%;">✨</div>
  <div class="star" style="top: 42%; left: 73%;">🌟</div>
  <div class="star" style="top: 55%; left: 25%;">✨</div>
  <div class="star" style="top: 58%; left: 28%;">🌟</div>
  <div class="star" style="top: 70%; left: 60%;">✨</div>
  <div class="star" style="top: 72%; left: 63%;">🌟</div>
  <div class="star" style="top: 80%; left: 10%;">✨</div>
  <div class="star" style="top: 83%; left: 13%;">🌟</div>
  <div class="star" style="top: 85%; left: 80%;">✨</div>
  <div class="star" style="top: 88%; left: 83%;">🌟</div>
  <div class="star" style="top: 20%; left: 85%;">✨</div>
  <div class="star" style="top: 23%; left: 88%;">🌟</div>
  <div class="star" style="top: 65%; left: 45%;">✨</div>
  <div class="star" style="top: 68%; left: 48%;">🌟</div>
  <div class="star" style="top: 35%; left: 5%;">✨</div>
  <div class="star" style="top: 38%; left: 8%;">🌟</div>

  <main class="container">
    <div class="card">
      <h2>✨ Tentang 🍀</h2>
      <p>Website ini dibuat Khusus untuk menunjukkan berbagai Karya yg dibuat oleh Danang.... 😙</p>
    </div>
    <div class="card">
      <h2>📸 Galeri SpesialZzZz Karya Danang....🥳🎉</h2>
      <p>Dari:(@Danang_Argus_Prime🗿)</p>
<video width="220" height="220" controls>
  <source src="Danang.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video width="220" height="220" controls>
  <source src="Shiroko.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video width="220" height="220" controls>
  <source src="Kuroko.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
    </div>

 <div class="card">
 <video width="220" height="220" controls>
  <source src="Hoshino.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video width="220" height="220" controls>
  <source src="Furina.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video width="220" height="220" controls>
  <source src="Chibi.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
   </div>
     

  </main>  
  
  <footer>  
    <p> © Copyright 2025 Leaf"Corp....Yang Copy-paste Website ini,semoga mendapatkan Balasan Yang setimpal....lagian Buat susah² diCopy Sama <b>OKUNUM</b> Tertentu ....😑🌟</p>  
  </footer>  
</body>  
</html>
