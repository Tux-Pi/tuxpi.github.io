<div class="tuxpi-hero-container">
    <!-- BACKGROUND SLIDER -->
    <div id="hero-slider" class="hero-slider">
        <!-- Le immagini vengono gestite via CSS/JS sotto -->
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    </div>
<!-- CONTENUTO -->
    <div class="hero-overlay">
        <div class="hero-content">
            <div class="hero-badge">PROGETTO TUXPI</div>
            <h1 class="hero-title">TUX<span>PI</span></h1>
            
<div class="typing-container">
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
// CONFIGURAZIONE SINCRONIZZATA
const phrases = [
    "Linux & Raspberry Pi",
    "Proxmox Homelab",
    "Virtualizzazione & Libertà"
];

const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');

let currentIndex = 0;
let charIndex = 0;
let isDeleting = false;
let typeSpeed = 100;

function updateSlides(index) {
    slides.forEach((slide, i) => {
        slide.classList.remove('active');
        if (i === index) slide.classList.add('active');
    });
}

function typeEffect() {
    const currentPhrase = phrases[currentIndex];
    
    if (isDeleting) {
        // CANCELLAZIONE
        textElement.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--;
        typeSpeed = 40; 
    } else {
        // SCRITTURA
        textElement.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++;
        typeSpeed = 120;
    }

    // LOGICA DI CAMBIO SINCRONIZZATO
    if (!isDeleting && charIndex === currentPhrase.length) {
        // Ha finito di scrivere: Aspetta 3 secondi prima di cancellare
        isDeleting = true;
        typeSpeed = 3000; 
    } else if (isDeleting && charIndex === 0) {
        // Ha finito di cancellare: CAMBIA IMMAGINE ORA
        isDeleting = false;
        currentIndex = (currentIndex + 1) % phrases.length;
        updateSlides(currentIndex); // <--- Sincronizzazione immagine
        typeSpeed = 500; 
    }

    setTimeout(typeEffect, typeSpeed);
}

document.addEventListener('DOMContentLoaded', () => {
    typeEffect();
});
</script>

<style>
/* 1. RESET E BREAKOUT MARGINI */
.tuxpi-hero-container {
    position: relative;
    width: 100vw;
    height: 95vh;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    margin-top: -3.5rem; /* Compensa navbar */
    overflow: hidden;
    background: #000;
}

/* 2. ANIMAZIONE IMMAGINI (Ken Burns + Fade) */
.hero-slider {
    position: absolute;
    inset: 0;
    z-index: 1;
}

.hero-slide {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    opacity: 0;
    transform: scale(1.1); /* Parte leggermente zoomato */
    transition: opacity 1.5s ease-in-out, transform 6s ease-in-out;
}

/* Quando la slide è attiva, diventa visibile e fa lo zoom inverso */
.hero-slide.active {
    opacity: 1;
    transform: scale(1);
    z-index: 2;
}

/* 3. TESTO E OVERLAY */
.hero-overlay {
    position: relative;
    z-index: 10;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.5) 90%);
}

.hero-content {
    text-align: center;
    color: white;
}

.hero-badge {
    color: #3b82f6;
    letter-spacing: 5px;
    font-weight: 800;
    font-size: 0.8rem;
    margin-bottom: 1rem;
    text-transform: uppercase;
}

.hero-title {
    font-size: clamp(5rem, 20vw, 12rem) !important;
    font-weight: 900 !important;
    line-height: 0.8;
    letter-spacing: -8px;
    margin: 0 !important;
}

.hero-title span { color: #3b82f6; }

.typing-container {
    margin-top: 2rem;
    height: 3.5rem;
    font-family: 'Courier New', monospace;
    font-size: clamp(1.2rem, 4vw, 2.5rem);
    color: #cbd5e1;
}

.cursor {
    animation: blink 0.8s infinite;
    color: #3b82f6;
    font-weight: bold;
}

@keyframes blink { 50% { opacity: 0; } }

/* 4. PULSANTI */
.hero-buttons {
    margin-top: 4rem;
    display: flex;
    gap: 20px;
    justify-content: center;
}

.btn {
    padding: 16px 40px;
    border-radius: 50px;
    font-weight: 800;
    text-decoration: none;
    text-transform: uppercase;
    transition: 0.4s;
    font-size: 0.9rem;
}

.btn-blue { background: #3b82f6; color: white; }
.btn-outline { border: 2px solid white; color: white; }
.btn:hover { 
    transform: translateY(-5px); 
    box-shadow: 0 10px 30px rgba(59, 130, 246, 0.4);
}

/* 5. PULIZIA TEMA HEXTRA */
.hextra-breadcrumb, .next-link, .prev-link, .mt-16, footer {
    display: none !important;
}
</style>
