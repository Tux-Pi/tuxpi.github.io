---
title: "TuxPi - Home"
---

<!-- 1. SLIDER GIGANTE A TUTTO SCHERMO -->
<div class="main-slider-container">
        <!-- Immagini dello Slider -->
    <div class="slide fade" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070');"></div>
    <div class="slide fade" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
    <div class="slide fade" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
 <!-- Contenuto Sopra lo Slider -->
    <div class="slider-overlay-content">
        <div class="hero-badge">PROGETTO OPEN SOURCE</div>
        <h1 class="hero-title">TUX<span>PI</span></h1>
        <div class="hero-subtitle">> <span class="typing"></span><span class="cursor">_</span></div>
        <div class="hero-buttons">
            <a href="/blog" class="btn btn-blue">Esplora Articoli</a>
            <a href="/docs" class="btn btn-outline">Documentazione</a>
        </div>
    </div>
</div>

<style>
/* RIMUOVE MARGINI E RENDE TUTTO GIGANTE */
.main-slider-container {
    position: relative;
    width: 100vw;
    height: 95vh;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    margin-top: -2rem;
    overflow: hidden;
    background: black;
}

/* LOGICA SLIDER */
.slide {
    position: absolute;
    width: 100%;
    height: 100%;
    background-size: cover;
    background-position: center;
    opacity: 0;
    transition: opacity 1.5s ease-in-out;
}

/* Animazione automatica delle slide (3 immagini) */
.slide:nth-child(1) { animation: cycle 15s infinite; }
.slide:nth-child(2) { animation: cycle 15s infinite 5s; }
.slide:nth-child(3) { animation: cycle 15s infinite 10s; }

@keyframes cycle {
    0%, 33% { opacity: 1; }
    40%, 100% { opacity: 0; }
}

/* CONTENUTO CENTRALE */
.slider-overlay-content {
    position: relative;
    z-index: 10;
    height: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 0 20px;
}

.hero-badge {
    color: #3b82f6;
    letter-spacing: 4px;
    font-weight: 800;
    font-size: 0.9rem;
    margin-bottom: 1rem;
}

.hero-title {
    font-size: clamp(5rem, 18vw, 12rem) !important;
    font-weight: 900 !important;
    color: white !important;
    line-height: 0.8 !important;
    margin: 0 !important;
    letter-spacing: -6px;
}

.hero-title span { color: #3b82f6; }

.hero-subtitle {
    font-family: 'Courier New', monospace;
    font-size: clamp(1.2rem, 3vw, 2rem);
    color: #e2e8f0;
    margin-top: 2rem;
}

/* EFFETTO SCRITTURA */
.typing::after {
    content: "";
    animation: type 12s infinite;
}

@keyframes type {
    0%, 25% { content: "Linux & Raspberry Pi"; }
    26%, 50% { content: "Proxmox Homelab"; }
    51%, 75% { content: "Virtualizzazione"; }
    76%, 100% { content: "Libertà Digitale"; }
}

.cursor { animation: blink 0.8s infinite; color: #3b82f6; }
@keyframes blink { 50% { opacity: 0; } }

/* BOTTONI */
.hero-buttons {
    margin-top: 4rem;
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
    justify-content: center;
}

.btn {
    padding: 18px 45px;
    border-radius: 50px;
    font-weight: 800;
    text-decoration: none;
    transition: 0.3s;
    text-transform: uppercase;
    font-size: 0.9rem;
}

.btn-blue { background: #3b82f6; color: white; }
.btn-outline { border: 2px solid white; color: white; }
.btn:hover { transform: scale(1.1); box-shadow: 0 0 30px rgba(59, 130, 246, 0.5); }

/* NASCONDE ELEMENTI STRANI DI HEXTRA NELLA HOME */
header + main .hextra-breadcrumb, 
header + main h1:first-of-type {
    display: none !important;
}
</style>
