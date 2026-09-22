```html
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>EL CARBONO | Huella, Contaminación y Descarbonización</title>

<style>
:root{
  --bg:#04130f;
  --bg2:#09261e;
  --card:rgba(255,255,255,.08);
  --text:#f3fff8;
  --muted:#b8d3c7;
  --green:#37e39a;
  --green2:#0bd37f;
  --cyan:#5ee7ff;
  --orange:#ffbd59;
  --red:#ff526d;
  --purple:#b98cff;
  --shadow:0 20px 60px rgba(0,0,0,.35);
}

*{
  box-sizing:border-box;
  margin:0;
  padding:0;
}

html{
  scroll-behavior:smooth;
}

body{
  font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;
  color:var(--text);

  background:
    radial-gradient(circle at 10% 10%,#15543d 0,transparent 28%),
    radial-gradient(circle at 90% 20%,#123b51 0,transparent 28%),
    linear-gradient(180deg,#04130f,#071b16 60%,#03100d);

  overflow-x:hidden;
}

/* =========================
   FONDO ANIMADO
========================= */

body:before{
  content:"";
  position:fixed;
  inset:0;
  pointer-events:none;
  opacity:.15;

  background-image:
    radial-gradient(#fff 1px,transparent 1px);

  background-size:45px 45px;

  animation:
    drift 25s linear infinite;
}

@keyframes drift{
  to{
    background-position:180px 180px;
  }
}

/* =========================
   NAVEGACIÓN
========================= */

nav{
  position:sticky;
  top:0;
  z-index:100;

  background:rgba(3,16,13,.78);
  backdrop-filter:blur(18px);

  border-bottom:1px solid rgba(255,255,255,.1);
}

.navin{
  max-width:1200px;
  margin:auto;
  padding:14px 20px;

  display:flex;
  align-items:center;
  justify-content:space-between;
}

.logo{
  font-weight:900;
  letter-spacing:.5px;
}

.logo span{
  color:var(--green);
}

nav a{
  color:var(--muted);
  text-decoration:none;
  margin-left:18px;
  font-size:.9rem;
  transition:.25s;
}

nav a:hover{
  color:white;
}

.sound-btn{
  margin-left:15px;
  border:1px solid rgba(255,255,255,.15);
  background:rgba(255,255,255,.08);
  color:white;
  border-radius:12px;
  padding:8px 12px;
  cursor:pointer;
}

/* =========================
   HERO
========================= */

.hero{
  min-height:88vh;
  display:grid;
  place-items:center;

  padding:80px 20px 50px;

  position:relative;
}

.hero-in{
  max-width:1200px;
  width:100%;

  display:grid;
  grid-template-columns:1.1fr .9fr;

  gap:50px;
  align-items:center;
}

.badge{
  display:inline-flex;
  gap:8px;

  padding:8px 13px;

  border:1px solid rgba(55,227,154,.35);
  border-radius:999px;

  background:rgba(55,227,154,.09);

  color:#caffea;

  font-size:.85rem;

  margin-bottom:18px;
}

h1{
  font-size:clamp(2.5rem,6vw,5.5rem);
  line-height:.95;
  letter-spacing:-4px;
}

h1 span{
  color:var(--green);

  text-shadow:
    0 0 35px rgba(55,227,154,.4);
}

.hero p{
  font-size:1.12rem;
  color:var(--muted);
  max-width:680px;

  line-height:1.7;

  margin:22px 0;
}

.btn{
  border:0;
  border-radius:14px;

  padding:13px 20px;

  font-weight:800;
  cursor:pointer;

  color:#052017;
  background:var(--green);

  box-shadow:
    0 8px 30px rgba(55,227,154,.2);

  transition:.25s;
}

.btn:hover{
  transform:
    translateY(-3px)
    scale(1.02);
}

.btn.secondary{
  background:rgba(255,255,255,.09);
  color:#fff;

  border:1px solid rgba(255,255,255,.13);

  margin-left:8px;
}

/* =========================
   PLANETA
========================= */

.globe{
  width:min(350px,75vw);
  aspect-ratio:1;

  border-radius:50%;

  margin:auto;

  position:relative;

  background:
    radial-gradient(
      circle at 35% 30%,
      #7affc5 0 2%,
      #218d67 12%,
      #116047 35%,
      #082f29 65%,
      #031714 100%
    );

  box-shadow:
    0 0 45px rgba(55,227,154,.35),
    inset -35px -25px 60px rgba(0,0,0,.45);

  animation:float 4s ease-in-out infinite;
}

.globe:before{
  content:"";

  position:absolute;
  inset:13%;

  border-radius:50%;

  border:
    2px dashed
    rgba(94,231,255,.45);

  animation:
    spin 14s linear infinite;
}

.globe:after{
  content:"🌱";

  position:absolute;

  font-size:5rem;

  left:50%;
  top:50%;

  transform:
    translate(-50%,-50%);

  filter:
    drop-shadow(
      0 0 15px
      rgba(55,227,154,.4)
    );
}

@keyframes float{
  50%{
    transform:translateY(-15px);
  }
}

@keyframes spin{
  to{
    transform:rotate(360deg);
  }
}

/* =========================
   SECCIONES
========================= */

section{
  max-width:1200px;
  margin:auto;

  padding:90px 20px;
}

.title{
  text-align:center;
  margin-bottom:42px;
}

.title h2{
  font-size:2.3rem;
}

.title p{
  color:var(--muted);
  margin-top:8px;
}

/* =========================
   TARJETAS
========================= */

.grid{
  display:grid;

  grid-template-columns:
    repeat(3,1fr);

  gap:18px;
}

.card{
  background:var(--card);

  border:
    1px solid
    rgba(255,255,255,.1);

  border-radius:22px;

  padding:25px;

  box-shadow:var(--shadow);

  transition:.35s;

  position:relative;

  overflow:hidden;
}

.card:hover{
  transform:
    translateY(-10px)
    scale(1.015);

  border-color:
    rgba(55,227,154,.5);

  box-shadow:
    0 25px 70px
    rgba(55,227,154,.12);
}

.icon{
  font-size:2.4rem;
  margin-bottom:14px;
}

.card h3{
  margin-bottom:8px;
}

.card p{
  color:var(--muted);
  line-height:1.6;
}

/* =========================
   REVEAL
========================= */

.reveal{
  opacity:0;
  transform:translateY(40px);

  transition:
    opacity .8s ease,
    transform .8s ease;
}

.reveal.show{
  opacity:1;
  transform:none;
}

/* =========================
   ESCENA DE CONTAMINACIÓN
========================= */

.pollution-scene{
  position:relative;

  height:560px;

  overflow:hidden;

  border-radius:30px;

  background:
    linear-gradient(
      180deg,
      #102f3c 0%,
      #163e42 48%,
      #214c35 49%,
      #071b16 100%
    );

  border:
    1px solid
    rgba(255,255,255,.12);

  box-shadow:var(--shadow);
}

/* SOL */

.sun{
  position:absolute;

  width:90px;
  height:90px;

  border-radius:50%;

  background:#ffd36b;

  right:80px;
  top:50px;

  box-shadow:
    0 0 60px
    rgba(255,190,80,.7);

  animation:
    sunPulse 3s infinite;
}

@keyframes sunPulse{
  50%{
    box-shadow:
      0 0 90px
      rgba(255,190,80,.9);
  }
}

/* CIUDAD */

.city{
  position:absolute;
  bottom:120px;
  left:0;
  width:100%;

  display:flex;
  align-items:end;
  justify-content:center;

  gap:8px;
}

.building{
  width:55px;

  background:
    linear-gradient(
      90deg,
      #172c2a,
      #29443e
    );

  border:
    1px solid
    rgba(255,255,255,.08);

  position:relative;
}

.building:nth-child(1){height:130px}
.building:nth-child(2){height:180px}
.building:nth-child(3){height:110px}
.building:nth-child(4){height:210px}
.building:nth-child(5){height:145px}
.building:nth-child(6){height:190px}
.building:nth-child(7){height:120px}

.building:after{
  content:"";

  position:absolute;
  inset:10px;

  background:
    repeating-linear-gradient(
      0deg,
      rgba(255,213,100,.65) 0 5px,
      transparent 5px 18px
    );
}

/* TERMOELÉCTRICA */

.powerplant{
  position:absolute;

  bottom:120px;
  left:8%;

  width:310px;
  height:220px;
}

.plant-body{
  position:absolute;

  bottom:0;
  left:30px;

  width:220px;
  height:130px;

  background:
    linear-gradient(
      145deg,
      #293d3a,
      #111f1d
    );

  border-radius:15px 15px 4px 4px;

  border:
    1px solid
    rgba(255,255,255,.15);
}

.plant-roof{
  position:absolute;

  bottom:115px;
  left:15px;

  width:250px;
  height:30px;

  background:#40504c;

  clip-path:
    polygon(
      0 100%,
      15% 0,
      85% 0,
      100% 100%
    );
}

.chimney{
  position:absolute;

  bottom:100px;

  width:38px;
  height:160px;

  background:
    repeating-linear-gradient(
      180deg,
      #6e716b 0 25px,
      #3f4441 25px 50px
    );

  border-radius:8px 8px 2px 2px;
}

.chimney.one{
  left:75px;
}

.chimney.two{
  left:170px;
}

/* HUMO */

.smoke{
  position:absolute;

  bottom:240px;

  width:35px;
  height:35px;

  border-radius:50%;

  background:
    rgba(100,105,105,.7);

  filter:blur(7px);

  animation:
    smokeRise 5s infinite;
}

.smoke.s1{
  left:77px;
}

.smoke.s2{
  left:172px;

  animation-delay:1.8s;
}

@keyframes smokeRise{
  0%{
    transform:
      translate(0,0)
      scale(.7);

    opacity:.7;
  }

  50%{
    transform:
      translate(30px,-110px)
      scale(1.7);

    opacity:.45;
  }

  100%{
    transform:
      translate(-20px,-230px)
      scale(3);

    opacity:0;
  }
}

/* CARRETERA */

.road{
  position:absolute;

  left:0;
  bottom:0;

  width:100%;
  height:120px;

  background:#101917;
}

.road:before{
  content:"";

  position:absolute;

  left:0;
  top:50%;

  width:100%;
  height:5px;

  background:
    repeating-linear-gradient(
      90deg,
      #e8d88b 0 70px,
      transparent 70px 130px
    );
}

/* AUTOS */

.car{
  position:absolute;

  width:70px;
  height:32px;

  bottom:65px;

  border-radius:12px 16px 7px 7px;

  background:#e54c52;

  animation:
    drive 8s linear infinite;
}

.car:before,
.car:after{
  content:"";

  position:absolute;

  width:15px;
  height:15px;

  background:#050808;

  border-radius:50%;

  bottom:-8px;
}

.car:before{
  left:8px;
}

.car:after{
  right:8px;
}

.car.two{
  background:#42b6e8;
  animation-duration:11s;
  animation-delay:-4s;
}

@keyframes drive{
  from{
    left:-100px;
  }

  to{
    left:110%;
  }
}

/* PARTICULAS */

.particle{
  position:absolute;

  width:7px;
  height:7px;

  border-radius:50%;

  background:
    rgba(94,231,255,.8);

  box-shadow:
    0 0 12px
    rgba(94,231,255,.8);

  animation:
    particleFloat 6s linear infinite;
}

@keyframes particleFloat{
  from{
    transform:
      translateY(0)
      scale(.5);

    opacity:0;
  }

  20%{
    opacity:1;
  }

  to{
    transform:
      translateY(-400px)
      translateX(80px)
      scale(1.5);

    opacity:0;
  }
}

.scene-label{
  position:absolute;

  left:25px;
  top:25px;

  max-width:420px;

  background:
    rgba(0,0,0,.4);

  backdrop-filter:blur(10px);

  border:
    1px solid
    rgba(255,255,255,.1);

  border-radius:18px;

  padding:18px;
}

.scene-label h3{
  margin-bottom:7px;
}

.scene-label p{
  color:var(--muted);
  line-height:1.5;
}

/* =========================
   CALCULADORA
========================= */

.calculator{
  max-width:850px;
  margin:auto;

  background:
    rgba(255,255,255,.08);

  border:
    1px solid
    rgba(255,255,255,.12);

  border-radius:28px;

  padding:30px;

  box-shadow:var(--shadow);
}

.row{
  margin:22px 0;
}

.row label{
  display:flex;
  justify-content:space-between;

  margin-bottom:10px;

  color:#dff8eb;
}

input[type=range]{
  width:100%;

  accent-color:var(--green);

  cursor:pointer;
}

.value{
  color:var(--green);
  font-weight:900;
}

.results{
  display:grid;

  grid-template-columns:
    repeat(3,1fr);

  gap:12px;

  margin-top:25px;
}

.result{
  background:
    rgba(0,0,0,.18);

  border-radius:18px;

  padding:20px;

  text-align:center;
}

.result b{
  display:block;

  font-size:1.7rem;

  margin-top:5px;
}

.result small{
  color:var(--muted);
}

.bar{
  height:15px;

  background:
    rgba(255,255,255,.1);

  border-radius:99px;

  overflow:hidden;

  margin-top:18px;
}

.bar i{
  display:block;

  height:100%;

  width:0;

  background:
    linear-gradient(
      90deg,
      var(--green),
      var(--cyan)
    );

  border-radius:99px;

  transition:1s;
}

/* =========================
   FUENTES
========================= */

.sources{
  display:grid;

  grid-template-columns:
    repeat(5,1fr);

  gap:15px;
}

.source{
  min-height:220px;

  padding:22px;

  border-radius:22px;

  background:
    rgba(255,255,255,.07);

  border:
    1px solid
    rgba(255,255,255,.1);

  text-align:center;

  cursor:pointer;

  transition:.35s;

  position:relative;

  overflow:hidden;
}

.source:hover{
  transform:
    translateY(-10px)
    rotateX(3deg);
}

.source .emoji{
  font-size:3.5rem;

  margin-bottom:15px;
}

.source h3{
  margin-bottom:8px;
}

.source p{
  color:var(--muted);

  font-size:.9rem;

  line-height:1.5;
}

.source.active{
  border-color:var(--green);

  box-shadow:
    0 0 35px
    rgba(55,227,154,.18);
}

/* =========================
   MODAL EDUCATIVO
========================= */

.modal{
  position:fixed;

  inset:0;

  background:
    rgba(0,0,0,.75);

  backdrop-filter:blur(10px);

  display:none;

  align-items:center;
  justify-content:center;

  z-index:200;

  padding:20px;
}

.modal.show{
  display:flex;
}

.modal-box{
  max-width:600px;
  width:100%;

  background:
    linear-gradient(
      145deg,
      #0d2b22,
      #061713
    );

  border:
    1px solid
    rgba(255,255,255,.15);

  border-radius:28px;

  padding:32px;

  box-shadow:
    0 30px 100px
    rgba(0,0,0,.6);

  animation:
    modalIn .35s ease;
}

@keyframes modalIn{
  from{
    transform:
      scale(.8)
      translateY(30px);

    opacity:0;
  }

  to{
    transform:
      scale(1)
      translateY(0);

    opacity:1;
  }
}

.close{
  float:right;

  border:0;

  background:
    rgba(255,255,255,.1);

  color:white;

  width:35px;
  height:35px;

  border-radius:50%;

  cursor:pointer;
}

.modal-icon{
  font-size:4rem;
  margin-bottom:10px;
}

.modal-box p{
  color:var(--muted);

  line-height:1.7;

  margin-top:15px;
}

/* =========================
   ENERGÍA
========================= */

.energy{
  display:grid;

  grid-template-columns:
    repeat(4,1fr);

  gap:14px;
}

.energy .card{
  text-align:center;
}

.energy .big{
  font-size:3rem;

  margin-bottom:10px;

  animation:
    energyFloat 3s ease-in-out infinite;
}

@keyframes energyFloat{
  50%{
    transform:
      translateY(-8px)
      rotate(3deg);
  }
}

/* =========================
   TRANSICIÓN
========================= */

.transition-box{
  max-width:1000px;

  margin:auto;

  padding:35px;

  border-radius:30px;

  background:
    linear-gradient(
      120deg,
      rgba(255,82,109,.1),
      rgba(55,227,154,.1)
    );

  border:
    1px solid
    rgba(255,255,255,.1);
}

.transition-slider{
  margin-top:25px;
}

.transition-slider input{
  width:100%;
}

.transition-world{
  height:300px;

  position:relative;

  overflow:hidden;

  border-radius:20px;

  margin-top:25px;

  background:
    linear-gradient(
      #192d37,
      #325344
    );

  transition:
    background 1s;
}

.factory-small{
  position:absolute;

  bottom:55px;
  left:15%;

  font-size:6rem;

  filter:
    drop-shadow(
      0 15px 15px
      rgba(0,0,0,.4)
    );
}

.tree{
  position:absolute;

  bottom:40px;

  font-size:5rem;

  right:15%;

  transform:
    scale(.5);

  opacity:.3;

  transition:
    1s;
}

.co2-cloud{
  position:absolute;

  top:30px;
  left:25%;

  font-size:2rem;

  transition:1s;
}

.transition-info{
  display:flex;

  justify-content:space-between;

  margin-top:15px;

  color:var(--muted);
}

/* =========================
   CONTADOR
========================= */

.counter-section{
  text-align:center;
}

.counter{
  font-size:clamp(3rem,8vw,7rem);

  font-weight:900;

  color:var(--green);

  text-shadow:
    0 0 40px
    rgba(55,227,154,.3);
}

/* =========================
   TOAST
========================= */

#toast{
  position:fixed;

  right:20px;
  bottom:20px;

  background:#eafff4;

  color:#06251a;

  padding:14px 18px;

  border-radius:14px;

  font-weight:800;

  transform:
    translateY(120px);

  transition:.4s;

  z-index:300;
}

#toast.on{
  transform:none;
}

/* =========================
   FOOTER
========================= */

footer{
  text-align:center;

  padding:55px 20px;

  color:var(--muted);

  border-top:
    1px solid
    rgba(255,255,255,.1);
}

/* =========================
   RESPONSIVE
========================= */

@media(max-width:900px){

  .hero-in{
    grid-template-columns:1fr;
    text-align:center;
  }

  .hero p{
    margin-left:auto;
    margin-right:auto;
  }

  .grid{
    grid-template-columns:
      1fr 1fr;
  }

  .energy{
    grid-template-columns:
      1fr 1fr;
  }

  .sources{
    grid-template-columns:
      1fr 1fr;
  }

  .pollution-scene{
    height:500px;
  }

  nav a{
    display:none;
  }
}

@media(max-width:550px){

  h1{
    letter-spacing:-2px;
  }

  .grid,
  .energy,
  .sources{
    grid-template-columns:1fr;
  }

  .results{
    grid-template-columns:1fr;
  }

  .calculator{
    padding:20px;
  }

  .pollution-scene{
    height:520px;
  }

  .powerplant{
    transform:scale(.75);
    transform-origin:left bottom;
  }

  .scene-label{
    right:15px;
    left:15px;
  }
}
</style>
</head>

<body>

<!-- =========================
     NAV
========================= -->

<nav>

<div class="navin">

<div class="logo">
🌎 EL <span>CARBONO</span>
</div>

<div>

<a href="#contaminacion">Contaminación</a>
<a href="#huella">Huella</a>
<a href="#fuentes">Fuentes</a>
<a href="#energia">Energía</a>
<a href="#acciones">Acciones</a>

<button
class="sound-btn"
id="soundBtn"
onclick="toggleSound()">
🔇 Sonido
</button>

</div>

</div>

</nav>


<!-- =========================
     HERO
========================= -->

<header class="hero">

<div class="hero-in">

<div>

<div class="badge">
🌱 Educación ambiental interactiva
</div>

<h1>
Comprende tu
<span>huella de carbono</span>
</h1>

<p>
Descubre de dónde vienen las emisiones de gases de efecto
invernadero, observa cómo funcionan algunas fuentes de
contaminación y explora cómo la descarbonización puede
transformar nuestro futuro.
</p>

<a
class="btn"
href="#contaminacion">
Explorar contaminación ↓
</a>

<a
class="btn secondary"
href="#huella">
Calcular mi huella
</a>

</div>


<div class="globe"
aria-label="Planeta Tierra animado">
</div>

</div>

</header>


<!-- =========================
     CONTAMINACIÓN
========================= -->

<section id="contaminacion">

<div class="title reveal">

<h2>
🏭 ¿De dónde vienen las emisiones?
</h2>

<p>
Observa una representación simplificada de una ciudad con
una central termoeléctrica, vehículos e industria.
</p>

</div>


<div class="pollution-scene reveal">

<div class="sun"></div>


<div class="scene-label">

<h3>
🔥 Combustibles fósiles
</h3>

<p>
Cuando se queman combustibles como carbón, petróleo o gas
natural, se libera principalmente CO₂. Las centrales
termoeléctricas pueden producir electricidad mediante
combustión y también emitir otros contaminantes atmosféricos.
</p>

</div>


<!-- TERMOELÉCTRICA -->

<div class="powerplant">

<div class="plant-roof"></div>

<div class="plant-body"></div>

<div class="chimney one"></div>

<div class="chimney two"></div>

<div class="smoke s1"></div>

<div class="smoke s2"></div>

</div>


<!-- CIUDAD -->

<div class="city">

<div class="building"></div>
<div class="building"></div>
<div class="building"></div>
<div class="building"></div>
<div class="building"></div>
<div class="building"></div>
<div class="building"></div>

</div>


<!-- CARRETERA -->

<div class="road"></div>

<div class="car"></div>

<div class="car two"></div>


<!-- PARTICULAS -->

<div class="particle"
style="left:45%;bottom:180px;animation-delay:0s">
</div>

<div class="particle"
style="left:55%;bottom:220px;animation-delay:1s">
</div>

<div class="particle"
style="left:65%;bottom:160px;animation-delay:2s">
</div>

<div class="particle"
style="left:75%;bottom:190px;animation-delay:3s">
</div>

</div>

</section>


<!-- =========================
     CONTADOR
========================= -->

<section class="counter-section">

<div class="title reveal">

<h2>
🌎 El carbono en nuestra vida diaria
</h2>

<p>
La energía, el transporte, la industria y el consumo están
conectados con las emisiones.
</p>

</div>

<div class="counter" id="counter">
0
</div>

<p style="color:var(--muted)">
kg de CO₂ simulados en este escenario
</p>

</section>


<!-- =========================
     FUENTES
========================= -->

<section id="fuentes">

<div class="title reveal">

<h2>
💨 Principales fuentes
</h2>

<p>
Haz clic en cada una para aprender qué ocurre.
</p>

</div>


<div class="sources">


<div
class="source reveal"
onclick="openInfo('🏭','Industria','Las industrias utilizan energía y procesos que pueden generar emisiones de CO₂ y otros contaminantes. La eficiencia energética y tecnologías más limpias pueden reducirlas.')">

<div class="emoji">🏭</div>

<h3>Industria</h3>

<p>
Procesos industriales y uso de energía.
</p>

</div>


<div
class="source reveal"
onclick="openInfo('⚡','Generación eléctrica','La electricidad puede producirse mediante diferentes tecnologías. Las centrales que queman combustibles fósiles liberan CO₂ durante la combustión.')">

<div class="emoji">⚡</div>

<h3>Electricidad</h3>

<p>
Depende de cómo se genere la energía.
</p>

</div>


<div
class="source reveal"
onclick="openInfo('🚗','Transporte','Los vehículos que utilizan gasolina o diésel liberan CO₂ al quemar combustibles. Caminar, pedalear, compartir viajes y usar transporte público pueden reducir el consumo de combustible.')">

<div class="emoji">🚗</div>

<h3>Transporte</h3>

<p>
Combustibles usados para desplazarnos.
</p>

</div>


<div
class="source reveal"
onclick="openInfo('🌾','Agricultura','La agricultura y la ganadería pueden generar gases de efecto invernadero como metano y óxido nitroso, además de emisiones asociadas al uso de energía y cambios de uso del suelo.')">

<div class="emoji">🌾</div>

<h3>Agricultura</h3>

<p>
Metano, óxido nitroso y uso del suelo.
</p>

</div>


<div
class="source reveal"
onclick="openInfo('🗑️','Residuos','Los residuos pueden generar emisiones durante su tratamiento y descomposición. Reducir, reutilizar, reciclar y mejorar la gestión de residuos ayuda a disminuir impactos.')">

<div class="emoji">🗑️</div>

<h3>Residuos</h3>

<p>
Emisiones relacionadas con su gestión.
</p>

</div>


</div>

</section>


<!-- =========================
     CALCULADORA
========================= -->

<section id="huella">

<div class="title reveal">

<h2>
🧮 Calculadora interactiva
</h2>

<p>
Mueve los controles y observa cómo cambia el escenario.
</p>

</div>


<div class="calculator reveal">


<div class="row">

<label>

⚡ Consumo eléctrico

<span class="value">
<span id="elecV">300</span>
kWh/mes
</span>

</label>

<input
id="elec"
type="range"
min="50"
max="1000"
value="300">

</div>


<div class="row">

<label>

🚗 Transporte

<span class="value">
<span id="transV">400</span>
km/mes
</span>

</label>

<input
id="trans"
type="range"
min="0"
max="2500"
value="400">

</div>


<div class="row">

<label>

🔥 Gas / combustibles

<span class="value">
<span id="gasV">20</span>
L/mes
</span>

</label>

<input
id="gas"
type="range"
min="0"
max="150"
value="20">

</div>


<div class="row">

<label>

🌞 Sustitución por renovables

<span class="value">
<span id="renV">43</span>%
</span>

</label>

<input
id="ren"
type="range"
min="0"
max="100"
value="43">

</div>


<button
class="btn"
onclick="calcular(true)">

🌱 Calcular escenario

</button>


<div class="results">

<div class="result">

Emisiones actuales

<b id="actual">
0.00
</b>

<small>
kg CO₂ / mes
</small>

</div>


<div class="result">

Emisiones evitadas

<b id="evitadas">
0.00
</b>

<small>
kg CO₂ / mes
</small>

</div>


<div class="result">

Emisiones finales

<b id="final">
0.00
</b>

<small>
kg CO₂ / mes
</small>

</div>

</div>


<div class="bar">
<i id="bar"></i>
</div>


<p
id="mensaje"
style="
text-align:center;
color:var(--muted);
margin-top:15px">
Ajusta los controles para explorar diferentes escenarios.
</p>

</div>

</section>


<!-- =========================
     TRANSICIÓN
========================= -->

<section>

<div class="title reveal">

<h2>
🌱 De la contaminación a la descarbonización
</h2>

<p>
Mueve el control y observa una transición visual.
</p>

</div>


<div class="transition-box reveal">


<div class="transition-world" id="transitionWorld">

<div class="factory-small">
🏭
</div>

<div class="co2-cloud" id="co2Cloud">
☁️ ☁️ ☁️
</div>

<div
class="tree"
id="tree">
🌳
</div>

</div>


<div class="transition-slider">

<input
id="transitionSlider"
type="range"
min="0"
max="100"
value="0"
oninput="transitionScene()">

</div>


<div class="transition-info">

<span>
🔥 Alta dependencia fósil
</span>

<span>
🌱 Mayor descarbonización
</span>

</div>


<p
id="transitionText"
style="
text-align:center;
color:var(--muted);
margin-top:20px">

Comienza a mover el control para explorar la transición.

</p>

</div>

</section>


<!-- =========================
     ENERGÍAS
========================= -->

<section id="energia">

<div class="title reveal">

<h2>
⚡ Energías que transforman el futuro
</h2>

<p>
Tecnologías que pueden formar parte de una transición energética.
</p>

</div>


<div class="energy">


<div class="card reveal">

<div class="big">
☀️
</div>

<h3>
Solar
</h3>

<p>
Convierte la radiación solar en electricidad mediante
tecnologías fotovoltaicas o termosolares.
</p>

</div>


<div class="card reveal">

<div class="big">
💨
</div>

<h3>
Eólica
</h3>

<p>
Aprovecha la energía cinética del viento para generar
electricidad.
</p>

</div>


<div class="card reveal">

<div class="big">
💧
</div>

<h3>
Hidroeléctrica
</h3>

<p>
Utiliza el movimiento del agua para producir electricidad.
</p>

</div>


<div class="card reveal">

<div class="big">
🌋
</div>

<h3>
Geotérmica
</h3>

<p>
Aprovecha el calor interno de la Tierra para generar energía.
</p>

</div>


</div>

</section>


<!-- =========================
     ACCIONES
========================= -->

<section id="acciones">

<div class="title reveal">

<h2>
🌱 Pequeñas acciones, gran impacto
</h2>

<p>
La descarbonización combina tecnología, eficiencia y cambios
en los sistemas de producción y consumo.
</p>

</div>


<div class="grid">


<div class="card reveal">

<div class="icon">
🔌
</div>

<h3>
Usa la energía eficientemente
</h3>

<p>
Apaga equipos que no necesites, mejora la eficiencia y,
cuando sea posible, utiliza tecnologías de menor consumo.
</p>

</div>


<div class="card reveal">

<div class="icon">
🚲
</div>

<h3>
Muévete de forma sostenible
</h3>

<p>
Caminar, utilizar bicicleta, compartir viajes o usar
transporte público puede disminuir el uso de combustibles.
</p>

</div>


<div class="card reveal">

<div class="icon">
♻️
</div>

<h3>
Reduce y reutiliza
</h3>

<p>
Consumir de manera responsable y prolongar la vida útil
de los productos puede reducir recursos y residuos asociados.
</p>

</div>


</div>

</section>


<!-- =========================
     MODAL
========================= -->

<div
class="modal"
id="infoModal"
onclick="closeModal(event)">

<div class="modal-box">

<button
class="close"
onclick="closeModal()">
×
</button>

<div
class="modal-icon"
id="modalIcon">
🏭
</div>

<h2 id="modalTitle">
Industria
</h2>

<p id="modalText">
Información.
</p>

</div>

</div>


<!-- =========================
     TOAST
========================= -->

<div id="toast">
🌱 ¡Escenario actualizado!
</div>


<footer>

🌎 <b>EL CARBONO</b>

<br><br>

Aprende · Calcula · Experimenta · Actúa

<br><br>

<small>
Esta experiencia utiliza factores simplificados con fines educativos.
Los resultados de una huella de carbono real dependen de los factores
de emisión, ubicación, tecnología y periodo analizado.
</small>

</footer>


<script>

/* =================================
   SONIDO CON WEB AUDIO API
================================= */

let audioContext = null;
let soundEnabled = false;

function initAudio(){

  if(!audioContext){

    audioContext =
      new (window.AudioContext ||
      window.webkitAudioContext)();

  }

}

function playTone(
  frequency=440,
  duration=.15,
  type="sine",
  volume=.04
){

  if(!soundEnabled) return;

  initAudio();

  const osc =
    audioContext.createOscillator();

  const gain =
    audioContext.createGain();

  osc.type=type;

  osc.frequency.value=frequency;

  gain.gain.setValueAtTime(
    volume,
    audioContext.currentTime
  );

  gain.gain.exponentialRampToValueAtTime(
    .001,
    audioContext.currentTime+duration
  );

  osc.connect(gain);
  gain.connect(audioContext.destination);

  osc.start();

  osc.stop(
    audioContext.currentTime+duration
  );
}

function toggleSound(){

  soundEnabled=!soundEnabled;

  const btn=
    document.getElementById("soundBtn");

  if(soundEnabled){

    initAudio();

    btn.textContent="🔊 Sonido ON";

    playTone(523,.15,"sine",.05);
    playTone(659,.18,"sine",.04);

  }else{

    btn.textContent="🔇 Sonido";

  }

}


/* =================================
   CONTROLES CALCULADORA
================================= */

const ids=[
  "elec",
  "trans",
  "gas",
  "ren"
];

ids.forEach(id=>{

  document
    .getElementById(id)
    .addEventListener(
      "input",
      ()=>{

        const value=
          document.getElementById(id).value;

        document
          .getElementById(id+"V")
          .textContent=value;

        calcular(false);

        if(id==="ren"){
          playTone(
            300 + value*5,
            .08,
            "sine",
            .02
          );
        }

      }
    );

});


/* =================================
   CALCULADORA
================================= */

function calcular(show=true){

  const elec=
    +document.getElementById("elec").value;

  const trans=
    +document.getElementById("trans").value;

  const gas=
    +document.getElementById("gas").value;

  const ren=
    +document.getElementById("ren").value;


  /*
    Factores simplificados para fines
    educativos.
  */

  const actual=
    elec*.40 +
    trans*.21 +
    gas*2.31;

  const evitadas=
    elec*.40*(ren/100);

  const final=
    Math.max(
      0,
      actual-evitadas
    );


  animateNumber(
    document.getElementById("actual"),
    actual
  );

  animateNumber(
    document.getElementById("evitadas"),
    evitadas
  );

  animateNumber(
    document.getElementById("final"),
    final
  );


  document
    .getElementById("bar")
    .style.width=
      Math.min(
        100,
        (evitadas/
        Math.max(actual,1))*100
      )+"%";


  let message="";

  if(ren>=70){

    message=
      "🌟 Gran escenario de sustitución por renovables.";

  }else if(ren>=40){

    message=
      "🌱 Buen avance: todavía existen oportunidades de reducción.";

  }else{

    message=
      "💡 Aumenta la sustitución por renovables para explorar una mayor reducción.";

  }

  document
    .getElementById("mensaje")
    .textContent=message;


  if(show){

    showToast();

    playTone(660,.12,"sine",.04);

    setTimeout(
      ()=>playTone(880,.15,"sine",.03),
      100
    );

  }

}


/* =================================
   CONTADOR ANIMADO
================================= */

let counterStarted=false;

function startCounter(){

  if(counterStarted) return;

  counterStarted=true;

  const target=1250;

  let current=0;

  const element=
    document.getElementById("counter");

  const interval=
    setInterval(()=>{

      current +=
        Math.ceil(
          (target-current)/15
        );

      element.textContent=
        current.toLocaleString(
          "es-CO"
        );

      if(current>=target){

        element.textContent=
          target.toLocaleString(
            "es-CO"
          );

        clearInterval(interval);

      }

    },35);

}


/* =================================
   ANIMAR NÚMEROS
================================= */

function animateNumber(
  element,
  target
){

  const start=
    parseFloat(
      element.textContent
    ) || 0;

  const duration=500;

  const startTime=
    performance.now();

  function update(time){

    const progress=
      Math.min(
        (time-startTime)/duration,
        1
      );

    const value=
      start+
      (target-start)*
      progress;

    element.textContent=
      value.toFixed(2);

    if(progress<1){

      requestAnimationFrame(update);

    }

  }

  requestAnimationFrame(update);

}


/* =================================
   TRANSICIÓN
================================= */

function transitionScene(){

  const value=
    +document
      .getElementById("transitionSlider")
      .value;

  const world=
    document
      .getElementById("transitionWorld");

  const tree=
    document
      .getElementById("tree");

  const cloud=
    document
      .getElementById("co2Cloud");

  const text=
    document
      .getElementById("transitionText");


  const green=
    Math.round(
      55+
      value*1.3
    );

  world.style.background=
    `linear-gradient(
      #${value>60?"78a9a0":"192d37"},
      #${value>60?"3f7655":"325344"}
    )`;


  tree.style.transform=
    `scale(${.5+
      value/100})`;

  tree.style.opacity=
    .3+
    value/140;


  cloud.style.opacity=
    1-value/100;


  if(value<25){

    text.textContent=
      "🔥 Alta dependencia de combustibles fósiles. Las emisiones siguen siendo elevadas.";

  }else if(value<50){

    text.textContent=
      "⚙️ Empiezan a incorporarse eficiencia y tecnologías de menor emisión.";

  }else if(value<75){

    text.textContent=
      "🌱 La participación de soluciones bajas en emisiones aumenta.";

  }else{

    text.textContent=
      "☀️🌬️ Mayor protagonismo de tecnologías renovables y eficiencia energética.";

  }

  playTone(
    250+
    value*5,
    .05,
    "sine",
    .015
  );

}


/* =================================
   MODAL
================================= */

function openInfo(
  icon,
  title,
  text
){

  document
    .getElementById("modalIcon")
    .textContent=icon;

  document
    .getElementById("modalTitle")
    .textContent=title;

  document
    .getElementById("modalText")
    .textContent=text;

  document
    .getElementById("infoModal")
    .classList.add("show");

  playTone(
    520,
    .15,
    "sine",
    .04
  );

}


function closeModal(event){

  if(
    event &&
    event.target !==
    document.getElementById("infoModal")
  ){

    return;

  }

  document
    .getElementById("infoModal")
    .classList.remove("show");

}


/* =================================
   TOAST
================================= */

function showToast(){

  const toast=
    document.getElementById("toast");

  toast.classList.add("on");

  setTimeout(
    ()=>{
      toast.classList.remove("on");
    },
    1800
  );

}


/* =================================
   INTERSECTION OBSERVER
================================= */

const observer=
  new IntersectionObserver(
    entries=>{

      entries.forEach(entry=>{

        if(entry.isIntersecting){

          entry.target
            .classList
            .add("show");

        }

      });

    },
    {
      threshold:.12
    }
  );


document
  .querySelectorAll(".reveal")
  .forEach(element=>{
    observer.observe(element);
  });


/* =================================
   CONTADOR AL APARECER
================================= */

const counterObserver=
  new IntersectionObserver(
    entries=>{

      if(entries[0].isIntersecting){

        startCounter();

      }

    },
    {
      threshold:.5
    }
  );


counterObserver.observe(
  document.getElementById("counter")
);


/* =================================
   INICIALIZAR
================================= */

calcular(false);

transitionScene();

</script>

</body>
</html>
```
