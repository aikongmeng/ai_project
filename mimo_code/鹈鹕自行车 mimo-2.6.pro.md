<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pelican Riding a Bicycle</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background: #2c3e50;
    overflow: hidden;
    font-family: sans-serif;
  }
  svg { width: 95vw; max-width: 1100px; height: auto; }

  @keyframes spin { to { transform: rotate(360deg); } }
  @keyframes bob {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-7px); }
  }
  @keyframes scrollRoad { to { transform: translateX(-120px); } }
  @keyframes drift {
    from { transform: translateX(0); }
    to { transform: translateX(-950px); }
  }
  @keyframes wingFlap {
    0%, 100% { transform: rotate(0deg); }
    50% { transform: rotate(-3deg); }
  }
  @keyframes tailSway {
    0%, 100% { transform: rotate(0deg); }
    50% { transform: rotate(4deg); }
  }
  @keyframes pouchBounce {
    0%, 100% { transform: scaleY(1); }
    50% { transform: scaleY(1.06); }
  }
  @keyframes floatNote {
    0% { opacity: 1; transform: translateY(0) scale(1); }
    100% { opacity: 0; transform: translateY(-60px) scale(0.6); }
  }

  .wheel-spin {
    animation: spin 0.65s linear infinite;
    transform-box: fill-box;
    transform-origin: center;
  }
  .pedal-spin {
    animation: spin 0.65s linear infinite;
    transform-box: fill-box;
    transform-origin: center;
  }
  .pelican-bob { animation: bob 0.325s ease-in-out infinite; }
  .road-scroll { animation: scrollRoad 0.65s linear infinite; }
  .cloud-drift { animation: drift 45s linear infinite; }
  .cloud-drift2 { animation: drift 55s linear infinite; animation-delay: -22s; }
  .wing-flap {
    animation: wingFlap 0.65s ease-in-out infinite;
    transform-box: fill-box;
    transform-origin: 0% 50%;
  }
  .tail-sway {
    animation: tailSway 0.325s ease-in-out infinite;
    transform-box: fill-box;
    transform-origin: 100% 50%;
  }
  .pouch-bounce {
    animation: pouchBounce 0.325s ease-in-out infinite;
    transform-box: fill-box;
    transform-origin: 50% 0%;
  }
  .note1 { animation: floatNote 2s ease-out infinite; }
  .note2 { animation: floatNote 2s ease-out 0.7s infinite; }
  .note3 { animation: floatNote 2s ease-out 1.4s infinite; }
</style>
</head>
<body>

<svg viewBox="0 0 900 550" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="skyGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#64B5F6"/>
      <stop offset="60%" stop-color="#90CAF9"/>
      <stop offset="100%" stop-color="#B3E5FC"/>
    </linearGradient>
    <linearGradient id="grassGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#7CB342"/>
      <stop offset="100%" stop-color="#558B2F"/>
    </linearGradient>
    <linearGradient id="roadGrad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#6D6D6D"/>
      <stop offset="100%" stop-color="#4A4A4A"/>
    </linearGradient>
    <linearGradient id="bodyGrad" x1="0" y1="0" x2="0.3" y2="1">
      <stop offset="0%" stop-color="#FFFFFF"/>
      <stop offset="55%" stop-color="#F5F5F5"/>
      <stop offset="100%" stop-color="#E0E0E0"/>
    </linearGradient>
    <linearGradient id="beakGrad" x1="0" y1="0" x2="1" y2="0.3">
      <stop offset="0%" stop-color="#FFA726"/>
      <stop offset="100%" stop-color="#E65100"/>
    </linearGradient>
    <linearGradient id="pouchGrad" x1="0.2" y1="0" x2="0.5" y2="1">
      <stop offset="0%" stop-color="#FFCC80"/>
      <stop offset="100%" stop-color="#FF9800"/>
    </linearGradient>
    <radialGradient id="sunGrad">
      <stop offset="0%" stop-color="#FFFDE7"/>
      <stop offset="50%" stop-color="#FFF176"/>
      <stop offset="100%" stop-color="#FFC107"/>
    </radialGradient>
    <radialGradient id="glowGrad">
      <stop offset="0%" stop-color="#FFF9C4" stop-opacity="0.6"/>
      <stop offset="100%" stop-color="#FFF9C4" stop-opacity="0"/>
    </radialGradient>
    <radialGradient id="cheekGrad">
      <stop offset="0%" stop-color="#F48FB1" stop-opacity="0.45"/>
      <stop offset="100%" stop-color="#F48FB1" stop-opacity="0"/>
    </radialGradient>
  </defs>

  <!-- ========== SKY ========== -->
  <rect width="900" height="550" fill="url(#skyGrad)"/>

  <!-- Sun -->
  <circle cx="770" cy="75" r="80" fill="url(#glowGrad)"/>
  <circle cx="770" cy="75" r="42" fill="url(#sunGrad)"/>

  <!-- ========== CLOUDS ========== -->
  <g class="cloud-drift" opacity="0.88">
    <ellipse cx="160" cy="95" rx="88" ry="30" fill="white"/>
    <ellipse cx="125" cy="82" rx="52" ry="26" fill="white"/>
    <ellipse cx="205" cy="80" rx="58" ry="28" fill="white"/>
    <ellipse cx="165" cy="70" rx="48" ry="24" fill="white"/>
    <ellipse cx="640" cy="68" rx="78" ry="26" fill="white" opacity="0.7"/>
    <ellipse cx="608" cy="58" rx="48" ry="22" fill="white" opacity="0.7"/>
    <ellipse cx="680" cy="55" rx="52" ry="24" fill="white" opacity="0.7"/>
    <ellipse cx="920" cy="108" rx="72" ry="24" fill="white" opacity="0.55"/>
    <ellipse cx="890" cy="97" rx="44" ry="20" fill="white" opacity="0.55"/>
    <ellipse cx="955" cy="95" rx="48" ry="22" fill="white" opacity="0.55"/>
  </g>
  <g class="cloud-drift2" opacity="0.5">
    <ellipse cx="350" cy="50" rx="65" ry="22" fill="white"/>
    <ellipse cx="325" cy="42" rx="40" ry="18" fill="white"/>
    <ellipse cx="380" cy="40" rx="44" ry="20" fill="white"/>
    <ellipse cx="820" cy="125" rx="58" ry="20" fill="white"/>
    <ellipse cx="795" cy="117" rx="38" ry="17" fill="white"/>
    <ellipse cx="850" cy="115" rx="42" ry="18" fill="white"/>
  </g>

  <!-- ========== HILLS ========== -->
  <ellipse cx="120" cy="432" rx="240" ry="90" fill="#81C784" opacity="0.35"/>
  <ellipse cx="780" cy="438" rx="270" ry="82" fill="#66BB6A" opacity="0.3"/>
  <ellipse cx="450" cy="442" rx="380" ry="75" fill="#A5D6A7" opacity="0.25"/>

  <!-- ========== GROUND ========== -->
  <rect x="0" y="432" width="900" height="118" fill="url(#grassGrad)"/>

  <!-- Grass tufts -->
  <g stroke="#558B2F" fill="none" stroke-width="1.5" opacity="0.35">
    <path d="M 45,448 Q 50,435 55,448"/><path d="M 130,452 Q 135,438 140,452"/>
    <path d="M 220,445 Q 225,432 230,445"/><path d="M 340,450 Q 345,437 350,450"/>
    <path d="M 710,447 Q 715,434 720,447"/><path d="M 820,451 Q 825,438 830,451"/>
    <path d="M 870,444 Q 875,431 880,444"/>
  </g>

  <!-- ========== ROAD ========== -->
  <rect x="0" y="468" width="900" height="48" fill="url(#roadGrad)"/>
  <!-- Road edge -->
  <rect x="0" y="468" width="900" height="3" fill="#3a3a3a"/>
  <rect x="0" y="513" width="900" height="3" fill="#3a3a3a"/>
  <!-- Scrolling center dashes -->
  <g class="road-scroll">
    <line x1="0" y1="492" x2="120" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="120" y1="492" x2="240" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="240" y1="492" x2="360" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="360" y1="492" x2="480" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="480" y1="492" x2="600" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="600" y1="492" x2="720" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="720" y1="492" x2="840" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="840" y1="492" x2="960" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
    <line x1="960" y1="492" x2="1080" y2="492" stroke="#FFEB3B" stroke-width="3.5" stroke-dasharray="32,28"/>
  </g>

  <!-- Shadow under bike -->
  <ellipse cx="465" cy="512" rx="220" ry="14" fill="#333" opacity="0.18"/>

  <!-- ==================== BICYCLE ==================== -->

  <!-- ===== Back Wheel ===== -->
  <g>
    <circle cx="310" cy="420" r="68" fill="none" stroke="#1a1a1a" stroke-width="13"/>
    <circle cx="310" cy="420" r="61" fill="none" stroke="#555" stroke-width="1.5"/>
    <g class="wheel-spin">
      <line x1="310" y1="352" x2="310" y2="488" stroke="#aaa" stroke-width="1.3"/>
      <line x1="242" y1="420" x2="378" y2="420" stroke="#aaa" stroke-width="1.3"/>
      <line x1="262" y1="372" x2="358" y2="468" stroke="#aaa" stroke-width="1.3"/>
      <line x1="358" y1="372" x2="262" y2="468" stroke="#aaa" stroke-width="1.3"/>
      <line x1="253" y1="393" x2="367" y2="447" stroke="#aaa" stroke-width="1"/>
      <line x1="253" y1="447" x2="367" y2="393" stroke="#aaa" stroke-width="1"/>
      <line x1="288" y1="355" x2="332" y2="485" stroke="#aaa" stroke-width="1"/>
      <line x1="288" y1="485" x2="332" y2="355" stroke="#aaa" stroke-width="1"/>
    </g>
    <circle cx="310" cy="420" r="11" fill="#666"/>
    <circle cx="310" cy="420" r="5" fill="#333"/>
  </g>

  <!-- ===== Front Wheel ===== -->
  <g>
    <circle cx="620" cy="420" r="68" fill="none" stroke="#1a1a1a" stroke-width="13"/>
    <circle cx="620" cy="420" r="61" fill="none" stroke="#555" stroke-width="1.5"/>
    <g class="wheel-spin">
      <line x1="620" y1="352" x2="620" y2="488" stroke="#aaa" stroke-width="1.3"/>
      <line x1="552" y1="420" x2="688" y2="420" stroke="#aaa" stroke-width="1.3"/>
      <line x1="572" y1="372" x2="668" y2="468" stroke="#aaa" stroke-width="1.3"/>
      <line x1="668" y1="372" x2="572" y2="468" stroke="#aaa" stroke-width="1.3"/>
      <line x1="563" y1="393" x2="677" y2="447" stroke="#aaa" stroke-width="1"/>
      <line x1="563" y1="447" x2="677" y2="393" stroke="#aaa" stroke-width="1"/>
      <line x1="598" y1="355" x2="642" y2="485" stroke="#aaa" stroke-width="1"/>
      <line x1="598" y1="485" x2="642" y2="355" stroke="#aaa" stroke-width="1"/>
    </g>
    <circle cx="620" cy="420" r="11" fill="#666"/>
    <circle cx="620" cy="420" r="5" fill="#333"/>
  </g>

  <!-- Chain -->
  <path d="M 312,420 Q 345,430 385,430 Q 405,430 412,425" fill="none" stroke="#555" stroke-width="2" stroke-dasharray="3,2"/>
  <path d="M 312,418 Q 345,410 385,408 Q 405,407 412,420" fill="none" stroke="#555" stroke-width="2" stroke-dasharray="3,2"/>

  <!-- Bicycle Frame -->
  <!-- Seat tube -->
  <line x1="345" y1="352" x2="380" y2="425" stroke="#D32F2F" stroke-width="8" stroke-linecap="round"/>
  <!-- Top tube -->
  <line x1="345" y1="352" x2="575" y2="342" stroke="#D32F2F" stroke-width="8" stroke-linecap="round"/>
  <!-- Down tube -->
  <line x1="380" y1="422" x2="575" y2="347" stroke="#D32F2F" stroke-width="8" stroke-linecap="round"/>
  <!-- Chain stay -->
  <line x1="380" y1="425" x2="310" y2="420" stroke="#C62828" stroke-width="6" stroke-linecap="round"/>
  <!-- Seat stay -->
  <line x1="345" y1="352" x2="310" y2="420" stroke="#C62828" stroke-width="6" stroke-linecap="round"/>
  <!-- Fork -->
  <line x1="575" y1="342" x2="620" y2="420" stroke="#D32F2F" stroke-width="8" stroke-linecap="round"/>
  <!-- Head tube -->
  <line x1="575" y1="342" x2="580" y2="322" stroke="#D32F2F" stroke-width="8" stroke-linecap="round"/>
  <!-- Frame highlight -->
  <line x1="352" y1="355" x2="570" y2="345" stroke="#EF5350" stroke-width="2" stroke-linecap="round" opacity="0.5"/>

  <!-- Seat -->
  <ellipse cx="340" cy="345" rx="30" ry="9" fill="#37474F" stroke="#263238" stroke-width="1.5"/>
  <rect x="335" y="345" width="10" height="14" rx="3" fill="#37474F"/>

  <!-- Handlebar stem -->
  <line x1="580" y1="322" x2="580" y2="305" stroke="#263238" stroke-width="6" stroke-linecap="round"/>
  <!-- Handlebar -->
  <path d="M 552,302 Q 580,294 608,302" fill="none" stroke="#263238" stroke-width="5.5" stroke-linecap="round" stroke-linejoin="round"/>
  <!-- Grips -->
  <line x1="545" y1="303" x2="558" y2="301" stroke="#4E342E" stroke-width="10" stroke-linecap="round"/>
  <line x1="602" y1="301" x2="615" y2="303" stroke="#4E342E" stroke-width="10" stroke-linecap="round"/>
  <!-- Bell -->
  <circle cx="568" cy="296" r="7" fill="#FFC107" stroke="#FFA000" stroke-width="1"/>
  <circle cx="568" cy="296" r="3" fill="#FFB300"/>

  <!-- Pedal crank assembly -->
  <g>
    <!-- Chainring -->
    <circle cx="412" cy="428" r="22" fill="none" stroke="#777" stroke-width="2.5"/>
    <circle cx="412" cy="428" r="16" fill="none" stroke="#777" stroke-width="1.2"/>
    <!-- Rotating crank + pedals -->
    <g class="pedal-spin">
      <!-- Crank arm down -->
      <line x1="412" y1="428" x2="412" y2="480" stroke="#555" stroke-width="5.5" stroke-linecap="round"/>
      <rect x="397" y="476" width="30" height="9" rx="3" fill="#222"/>
      <!-- Crank arm up -->
      <line x1="412" y1="428" x2="412" y2="376" stroke="#555" stroke-width="5.5" stroke-linecap="round"/>
      <rect x="397" y="370" width="30" height="9" rx="3" fill="#222"/>
    </g>
    <circle cx="412" cy="428" r="8" fill="#666"/>
    <circle cx="412" cy="428" r="3.5" fill="#333"/>
  </g>

  <!-- ==================== PELICAN ==================== -->
  <g class="pelican-bob">

    <!-- Tail feathers -->
    <g class="tail-sway">
      <path d="M 318,288 Q 298,280 278,276 Q 292,286 282,293 Q 300,300 318,296" fill="#E8E8E8" stroke="#BDBDBD" stroke-width="1"/>
      <path d="M 318,292 Q 292,290 272,294 Q 294,297 276,304 Q 302,306 318,302" fill="#DCDCDC" stroke="#BDBDBD" stroke-width="1"/>
    </g>

    <!-- Body -->
    <ellipse cx="362" cy="300" rx="54" ry="44" fill="url(#bodyGrad)" stroke="#BDBDBD" stroke-width="1.5"/>
    <!-- Body highlight -->
    <ellipse cx="352" cy="286" rx="32" ry="24" fill="white" opacity="0.35"/>
    <!-- Belly -->
    <ellipse cx="370" cy="318" rx="38" ry="22" fill="#ECEFF1" opacity="0.45"/>

    <!-- Neck -->
    <path d="M 388,272 Q 405,248 418,235 Q 432,222 440,216" fill="none" stroke="#E8E8E8" stroke-width="22" stroke-linecap="round"/>
    <path d="M 388,272 Q 405,248 418,235 Q 432,222 440,216" fill="none" stroke="#BDBDBD" stroke-width="1.2" stroke-linecap="round"/>
    <path d="M 393,268 Q 408,248 420,236 Q 433,224 440,218" fill="none" stroke="white" stroke-width="7" stroke-linecap="round" opacity="0.25"/>

    <!-- Head -->
    <circle cx="444" cy="212" r="25" fill="url(#bodyGrad)" stroke="#BDBDBD" stroke-width="1.5"/>
    <!-- Head top crest -->
    <ellipse cx="440" cy="193" rx="16" ry="10" fill="#F5F5F5" stroke="#BDBDBD" stroke-width="1"/>
    <path d="M 430,192 Q 437,185 444,188 Q 451,184 456,191" fill="none" stroke="#E0E0E0" stroke-width="1.5" stroke-linecap="round"/>

    <!-- Eye -->
    <circle cx="455" cy="207" r="7" fill="white" stroke="#333" stroke-width="1.5"/>
    <circle cx="456" cy="206" r="4" fill="#222"/>
    <circle cx="457.5" cy="204.5" r="1.8" fill="white"/>
    <circle cx="454" cy="208.5" r="1" fill="white" opacity="0.5"/>
    <!-- Eyebrow -->
    <path d="M 449,199 Q 455,196 462,198" fill="none" stroke="#333" stroke-width="1.8" stroke-linecap="round"/>

    <!-- Cheek blush -->
    <ellipse cx="447" cy="217" rx="9" ry="5.5" fill="url(#cheekGrad)"/>

    <!-- Beak - Upper mandible -->
    <path d="M 462,209 Q 510,214 568,224 Q 572,226 568,228 Q 510,222 462,216 Z" fill="url(#beakGrad)" stroke="#BF360C" stroke-width="1"/>
    <!-- Beak tip hook -->
    <path d="M 563,225 Q 573,222 572,228 Q 571,231 566,229" fill="#BF360C" stroke="#BF360C" stroke-width="0.5"/>
    <!-- Beak nostril -->
    <ellipse cx="478" cy="213" rx="2.5" ry="1.5" fill="#BF360C" opacity="0.6"/>

    <!-- Beak - Lower mandible & Pouch -->
    <g class="pouch-bounce">
      <path d="M 464,216 Q 510,222 568,228 Q 565,258 538,275 Q 510,288 482,275 Q 465,252 464,216 Z" fill="url(#pouchGrad)" stroke="#BF360C" stroke-width="1"/>
      <!-- Pouch highlight -->
      <path d="M 490,238 Q 518,244 542,246 Q 532,265 510,272 Q 492,262 488,246 Z" fill="#FFD54F" opacity="0.25"/>
      <!-- Pouch wrinkle lines -->
      <path d="M 478,245 Q 505,252 530,253" fill="none" stroke="#E65100" stroke-width="0.8" opacity="0.3"/>
      <path d="M 482,260 Q 505,266 522,265" fill="none" stroke="#E65100" stroke-width="0.8" opacity="0.25"/>
    </g>

    <!-- Wing (reaching to handlebar) -->
    <g class="wing-flap">
      <path d="M 382,278 Q 420,272 470,288 Q 510,300 548,306 Q 553,307 552,310
               Q 540,316 515,318 Q 468,322 425,312 Q 395,302 382,295 Z"
            fill="#E0E0E0" stroke="#BDBDBD" stroke-width="1"/>
      <!-- Feather details -->
      <path d="M 400,288 Q 445,300 495,312" fill="none" stroke="#CCC" stroke-width="1" stroke-linecap="round"/>
      <path d="M 392,298 Q 438,310 482,316" fill="none" stroke="#CCC" stroke-width="1" stroke-linecap="round"/>
      <path d="M 408,283 Q 452,292 500,304" fill="none" stroke="#CCC" stroke-width="0.8" stroke-linecap="round"/>
      <!-- Wing tip fingers -->
      <path d="M 548,306 Q 556,302 558,306 Q 558,310 552,310" fill="#E0E0E0" stroke="#BDBDBD" stroke-width="1"/>
      <path d="M 542,310 Q 552,312 554,316 Q 550,318 544,315" fill="#E0E0E0" stroke="#BDBDBD" stroke-width="1"/>
    </g>

    <!-- Legs & Feet -->
    <!-- Right leg (forward) -->
    <line x1="388" y1="338" x2="408" y2="422" stroke="#FF8F00" stroke-width="7" stroke-linecap="round"/>
    <line x1="388" y1="338" x2="408" y2="422" stroke="#FFB300" stroke-width="3" stroke-linecap="round"/>
    <!-- Right webbed foot -->
    <path d="M 396,420 L 388,430 L 396,428 L 400,432 L 407,428 L 412,432 L 420,428 L 418,420 Z"
          fill="#FF8F00" stroke="#E65100" stroke-width="1"/>

    <!-- Left leg (back) -->
    <line x1="372" y1="336" x2="388" y2="418" stroke="#FF8F00" stroke-width="7" stroke-linecap="round"/>
    <line x1="372" y1="336" x2="388" y2="418" stroke="#FFB300" stroke-width="3" stroke-linecap="round"/>
    <!-- Left webbed foot -->
    <path d="M 376,416 L 368,426 L 376,424 L 380,428 L 387,424 L 392,428 L 400,424 L 398,416 Z"
          fill="#FF8F00" stroke="#E65100" stroke-width="1"/>

  </g>

  <!-- ========== MUSIC NOTES (floating up) ========== -->
  <g fill="#FF6F00" opacity="0.6" font-size="22" font-family="serif">
    <text class="note1" x="590" y="280">♪</text>
    <text class="note2" x="610" y="260">♫</text>
    <text class="note3" x="580" y="245">♪</text>
  </g>

  <!-- ========== SPEED LINES (behind bike) ========== -->
  <g stroke="#90A4AE" stroke-width="2" stroke-linecap="round" opacity="0.25">
    <line x1="220" y1="370" x2="175" y2="370"/>
    <line x1="230" y1="395" x2="185" y2="395"/>
    <line x1="215" y1="420" x2="170" y2="420"/>
    <line x1="235" y1="445" x2="195" y2="445"/>
  </g>

</svg>

</body>
</html>
