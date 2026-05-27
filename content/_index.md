---
title: "TuxPi - Home"
---

<div class="main-slider-container">
    <!-- 1. BACKGROUND SLIDER (Immagini che cambiano) -->
    <div class="slideshow">
        <div class="slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070');"></div>
        <div class="slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
        <div class="slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    </div>
<!-- 2. CONTENUTO CENTRALE -->
    <div class="hero-overlay">
        <div class="hero-content">
            <h1 class="hero-title">TUX<span>PI</span></h1>
            <!-- CONTENITORE TESTO TYPING -->
            <div class="typing-wrapper">
                <span class="prefix">> </span>
                <span id="typing-text"></span>
                <span class="cursor">_</span>
            </div>

<div class="hero-buttons">
                <a href="/blog" class="btn btn-blue">Articoli</a>
                <a href="/docs" class="btn btn-outline">Guide Tech</a>
            </div>
        </div>
    </div>
</div>

<script>
// CONFIGURAZIONE TYPING EFFECT
const textElement = document.getElementById('typing-text');
const phrases = [
    "Linux & Raspberry Pi",
    "Proxmox Homelab",
    "Virtualizzazione & Libertà",
    "Addio Windows 10"
];

let phraseIndex = 0;
let charIndex = 0;
let isDeleting = false;
let typeSpeed = 100;

function type() {
    const currentPhrase = phrases[phraseIndex];
    
    if (isDeleting) {
        // Cancella testo
        textElement.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--;
        typeSpeed = 50; // Più veloce a cancellare
    } else {
        // Scrive testo
        textElement.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++;
        typeSpeed = 150; // Velocità normale scrittura
    }

    // Logica di pausa e inversione
    if (!isDeleting && charIndex === currentPhrase.length) {
        isDeleting = true;
        typeSpeed = 2000; // Pausa quando ha finito di scrivere
    } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        phraseIndex = (phraseIndex + 1) % phrases.length;
        typeSpeed = 500; // Pausa prima di iniziare la nuova frase
    }

    setTimeout(type, typeSpeed);
}

// Avvia l'effetto al caricamento
document.addEventListener('DOMContentLoaded', type);
</script>

<style>
/* FULL WIDTH BREAKOUT */
.main-slider-container {
    position: relative;
    width: 100vw;
    height: 100vh; /* Copre quasi tutto lo schermo */
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    margin-top: -3.5rem; /* Compensa la navbar di Hextra */
    background: #000;
    overflow: hidden;
}

/* SLIDESHOW CSS */
.slideshow {
    position: absolute;
    inset: 0;
    z-index: 1;
}

.slide {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    opacity: 0;
    transition: transform 6s ease-in-out; /* Effetto zoom lento */
    animation: imageFade 16s infinite;
}

/* Sincronizzazione 4 immagini (4s l'una) */
.slide:nth-child(1) { animation-delay: 0s; }
.slide:nth-child(2) { animation-delay: 4s; }
.slide:nth-child(3) { animation-delay: 8s; }
/* Se ne aggiungi una quarta: .slide:nth-child(4) { animation-delay: 12s; } */

@keyframes imageFade {
    0%, 25% { opacity: 1; transform: scale(1); }
    30%, 100% { opacity: 0; transform: scale(1.1); }
}

/* OVERLAY E TESTO */
.hero-overlay {
    position: absolute;
    inset: 0;
    z-index: 10;
    display: flex;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.4) 80%);
}

.hero-content {
    text-align: center;
    color: white;
}

.hero-title {
    font-size: clamp(5rem, 20vw, 13rem) !important;
    font-weight: 900 !important;
    letter-spacing: -8px;
    margin: 0 !important;
    line-height: 0.8;
}

.hero-title span { color: #3b82f6; }

/* TYPING WRAPPER */
.typing-wrapper {
    margin-top: 2rem;
    font-family: 'Courier New', monospace;
    font-size: clamp(1.5rem, 4vw, 3rem);
    height: 4rem;
    color: #e2e8f0;
}

.cursor {
    color: #3b82f6;
    animation: blink 0.8s infinite;
    font-weight: bold;
}

@keyframes blink { 50% { opacity: 0; } }

/* BOTTONI */
.hero-buttons {
    margin-top: 3rem;
    display: flex;
    gap: 20px;
    justify-content: center;
}

.btn {
    padding: 15px 40px;
    border-radius: 50px;
    font-weight: 800;
    text-decoration: none;
    text-transform: uppercase;
    transition: 0.3s;
}

.btn-blue { background: #3b82f6; color: white; }
.btn-outline { border: 2px solid white; color: white; }
.btn:hover { transform: translateY(-5px); box-shadow: 0 10px 20px rgba(0,0,0,0.4); }

/* NASCONDE ELEMENTI HEXTRA */
.hextra-breadcrumb, .next-link, .prev-link, footer, .mt-16 {
    display: none !important;
}
</style>
