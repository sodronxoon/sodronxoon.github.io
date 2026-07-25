<center><iframe src="button.html"></iframe></center>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>SODRON</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html,
body {
    width: 100%;
    height: 100%;
    overflow: hidden;
    background: #fff;
}

body {
    font-family: Arial, Helvetica, sans-serif;
}

/* =========================================
   LAYAR UTAMA
   Total 15 detik:
   0 - 2   = putih
   2 - 14  = SODRON tampil
   14 - 15 = menghilang
   ========================================= */

.scene {
    position: relative;

    width: 100vw;
    height: 100vh;
    height: 100svh;

    display: flex;
    justify-content: center;
    align-items: center;

    overflow: hidden;

    background: #fff;
}


/* =========================================
   MY NAME IS
   ========================================= */

.intro {
    position: absolute;

    z-index: 10;

    text-align: center;

    opacity: 0;

    animation:
        introAnimation
        15s
        ease-in-out
        infinite;
}

.intro span {
    display: block;

    color: #111;

    font-size: clamp(
        18px,
        4vw,
        42px
    );

    font-weight: 300;

    letter-spacing: clamp(
        6px,
        2vw,
        18px
    );

    text-indent: clamp(
        6px,
        2vw,
        18px
    );
}


/* =========================================
   SODRON
   ========================================= */

.name {
    position: absolute;

    z-index: 9;

    text-align: center;

    opacity: 0;

    animation:
        sodronAnimation
        15s
        cubic-bezier(.12,.8,.2,1)
        infinite;
}

.name h1 {
    position: relative;

    color: #080808;

    font-size: clamp(
        55px,
        15vw,
        190px
    );

    font-weight: 1000;

    line-height: .85;

    letter-spacing: clamp(
        2px,
        1vw,
        14px
    );

    text-shadow:
        0 0 5px rgba(0,0,0,.25),
        0 0 20px rgba(0,0,0,.20),
        0 0 50px rgba(0,0,0,.10);
}


/* =========================================
   CAHAYA MENYAPU SODRON
   ========================================= */

.name h1::after {
    content: "SODRON";

    position: absolute;

    inset: 0;

    color: transparent;

    background:
        linear-gradient(
            110deg,
            transparent 20%,
            rgba(255,255,255,.1) 35%,
            #fff 48%,
            rgba(255,255,255,.1) 60%,
            transparent 80%
        );

    background-size: 250% 100%;

    background-clip: text;
    -webkit-background-clip: text;

    animation:
        shine
        2s
        linear
        infinite;
}


/* =========================================
   SHOCKWAVE
   ========================================= */

.wave {
    position: absolute;

    left: 50%;
    top: 50%;

    width: 30px;
    height: 30px;

    transform:
        translate(-50%, -50%);

    border:
        3px solid #111;

    border-radius: 50%;

    opacity: 0;

    z-index: 4;

    animation:
        waveAnimation
        15s
        ease-out
        infinite;
}


/* Lingkaran kedua */

.wave::before {
    content: "";

    position: absolute;

    inset: -5px;

    border:
        2px solid #777;

    border-radius: 50%;

    animation:
        innerWave
        15s
        ease-out
        infinite;
}


/* =========================================
   PARTICLES
   ========================================= */

.particles {
    position: absolute;

    inset: 0;

    z-index: 5;

    pointer-events: none;
}

.particle {
    position: absolute;

    left: 50%;
    top: 50%;

    width: 4px;
    height: 4px;

    border-radius: 50%;

    background: #111;

    opacity: 0;

    animation:
        particleAnimation
        15s
        cubic-bezier(.1,.8,.2,1)
        infinite;
}


/* =========================================
   FLASH
   ========================================= */

.flash {
    position: absolute;

    inset: 0;

    z-index: 20;

    background: white;

    opacity: 0;

    pointer-events: none;

    animation:
        flashAnimation
        15s
        ease-out
        infinite;
}


/* =========================================
   VIGNETTE
   ========================================= */

.vignette {
    position: absolute;

    inset: 0;

    z-index: 15;

    pointer-events: none;

    background:
        radial-gradient(
            ellipse at center,
            transparent 35%,
            rgba(0,0,0,.05) 100%
        );

    opacity: 0;

    animation:
        vignetteAnimation
        15s
        ease-in-out
        infinite;
}


/* =========================================
   ANIMASI MY NAME IS

   0 - 13.3%  = 0 - 2 detik putih
   13.3%       = mulai muncul
   20%         = selesai masuk
   86%         = mulai hilang
   100%        = kembali putih
   ========================================= */

@keyframes introAnimation {

    /* 0 detik */
    0% {
        opacity: 0;

        transform:
            translateY(30px);

        filter: blur(20px);
    }

    /* 2 detik */
    13.33% {
        opacity: 0;

        transform:
            translateY(30px);

        filter: blur(20px);
    }

    /* Masuk */
    17% {
        opacity: 1;

        transform:
            translateY(-80px);

        filter: blur(0);
    }

    /* Tetap tampil selama 12 detik */
    20%,
    86% {
        opacity: 1;

        transform:
            translateY(-90px);

        filter: blur(0);
    }

    /* Mulai hilang */
    93% {
        opacity: 0;

        transform:
            translateY(-125px);

        filter: blur(20px);
    }

    /* Kembali putih */
    100% {
        opacity: 0;

        transform:
            translateY(-125px);

        filter: blur(20px);
    }
}


/* =========================================
   ANIMASI SODRON
   ========================================= */

@keyframes sodronAnimation {

    /* Layar putih */
    0% {
        opacity: 0;

        transform:
            scale(.15)
            rotateX(40deg);

        filter: blur(35px);
    }

    /* 2 detik */
    13.33% {
        opacity: 0;

        transform:
            scale(.15)
            rotateX(40deg);

        filter: blur(35px);
    }

    /* Muncul */
    17% {
        opacity: 1;

        transform:
            scale(1.18)
            rotateX(0deg);

        filter: blur(0);
    }

    /* Sedikit bounce */
    19% {
        transform:
            scale(.96);
    }

    21% {
        transform:
            scale(1.03);
    }

    /* Tetap muncul */
    23%,
    86% {
        opacity: 1;

        transform:
            scale(1);

        filter: blur(0);
    }

    /* Menghilang */
    93% {
        opacity: 0;

        transform:
            scale(1.3);

        filter: blur(25px);
    }

    /* Reset */
    100% {
        opacity: 0;

        transform:
            scale(1.3);

        filter: blur(25px);
    }
}


/* =========================================
   CAHAYA BERGERAK
   ========================================= */

@keyframes shine {

    0% {
        background-position:
            150% 0;
    }

    100% {
        background-position:
            -150% 0;
    }
}


/* =========================================
   SHOCKWAVE
   ========================================= */

@keyframes waveAnimation {

    /* Putih 2 detik */
    0%,
    13.33% {
        width: 30px;
        height: 30px;

        opacity: 0;
    }

    /* Ledakan */
    14% {
        width: 50px;
        height: 50px;

        opacity: .9;
    }

    /* Membesar */
    25% {
        width: 160vw;
        height: 160vw;

        opacity: 0;
    }

    /* Tetap hilang */
    100% {
        opacity: 0;
    }
}


@keyframes innerWave {

    0%,
    13.33% {
        transform: scale(.2);

        opacity: 0;
    }

    14% {
        transform: scale(1);

        opacity: .8;
    }

    25% {
        transform: scale(15);

        opacity: 0;
    }

    100% {
        opacity: 0;
    }
}


/* =========================================
   PARTICLE EXPLOSION
   ========================================= */

@keyframes particleAnimation {

    /* Putih */
    0%,
    13.33% {
        opacity: 0;

        transform:
            translate(-50%, -50%)
            scale(.2);
    }

    /* Ledakan */
    14% {
        opacity: 1;
    }

    20% {
        opacity: .9;
    }

    /* Menyebar */
    35% {
        opacity: 0;

        transform:
            translate(
                calc(-50% + var(--x)),
                calc(-50% + var(--y))
            )
            scale(0);
    }

    100% {
        opacity: 0;
    }
}


/* =========================================
   FLASH
   ========================================= */

@keyframes flashAnimation {

    0%,
    13.33% {
        opacity: 0;
    }

    14% {
        opacity: .9;
    }

    15.5% {
        opacity: 0;
    }

    100% {
        opacity: 0;
    }
}


/* =========================================
   VIGNETTE
   ========================================= */

@keyframes vignetteAnimation {

    0%,
    13.33% {
        opacity: 0;
    }

    18%,
    86% {
        opacity: 1;
    }

    93%,
    100% {
        opacity: 0;
    }
}


/* =========================================
   RESPONSIVE HP
   ========================================= */

@media (max-width: 600px) {

    .name h1 {
        font-size: 17vw;

        letter-spacing: 4px;
    }

    .intro span {
        font-size: 18px;

        letter-spacing: 7px;

        text-indent: 7px;
    }
}


/* =========================================
   TABLET
   ========================================= */

@media (
    min-width: 601px
) and (
    max-width: 1000px
) {

    .name h1 {
        font-size: 14vw;
    }
}

</style>
</head>


<body>

<div class="scene">

    <!-- FLASH -->
    <div class="flash"></div>


    <!-- MY NAME IS -->
    <div class="intro">
        <span>MY NAME IS</span>
    </div>


    <!-- SODRON -->
    <div class="name">
        <h1>SODRON</h1>
    </div>


    <!-- SHOCKWAVE -->
    <div class="wave"></div>


    <!-- PARTICLES -->
    <div
        class="particles"
        id="particles">
    </div>


    <!-- VIGNETTE -->
    <div class="vignette"></div>

</div>


<script>

/* =========================================
   MEMBUAT PARTIKEL
   ========================================= */

const particles =
    document.getElementById("particles");


for (let i = 0; i < 150; i++) {

    const particle =
        document.createElement("div");

    particle.className =
        "particle";


    /* Arah acak */

    const angle =
        Math.random() *
        Math.PI *
        2;


    /* Jarak acak */

    const distance =
        150 +
        Math.random() *
        700;


    const x =
        Math.cos(angle) *
        distance;


    const y =
        Math.sin(angle) *
        distance;


    particle.style.setProperty(
        "--x",
        `${x}px`
    );

    particle.style.setProperty(
        "--y",
        `${y}px`
    );


    /* Ukuran */

    const size =
        1 +
        Math.random() * 5;


    particle.style.width =
        size + "px";

    particle.style.height =
        size + "px";


    /*
       Delay sangat kecil
       agar ledakan terasa natural
    */

    particle.style.animationDelay =
        (Math.random() * .15) + "s";


    particles.appendChild(
        particle
    );
}

</script>

</body>
</html>
