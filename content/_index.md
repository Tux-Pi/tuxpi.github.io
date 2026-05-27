
<div class="tuxpi-hero-container">
    <!-- BACKGROUND SLIDER -->
    <div id="hero-slider" class="hero-slider">
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    </div>
<!-- CONTENUTO HERO -->
    <div class="hero-overlay">
        <div class="hero-content">
            <h1 class="hero-title">TUX<span>PI</span></h1>
            <div class="typing-container">
                <span class="prefix">> </span>
                <span id="typing-text"></span>
                <span class="cursor">_</span>
            </div>
            <div class="hero-buttons">
                <a href="#articoli" class="btn btn-blue">Ultimi Articoli</a>
                <a href="#sezioni" class="btn btn-outline">Esplora Sezioni</a>
            </div>
        </div>
    </div>
</div>

<div class="home-content-wrapper">

# 🐧 Benvenuto su TuxPi!
In questo blog esploriamo la tecnologia **Linux**, con un focus particolare sul **Software Libero** e l'ottimizzazione dell'hardware. Che tu voglia resuscitare un vecchio PC o costruire un datacenter domestico, sei nel posto giusto.

<div id="sezioni" class="section-title">
    <h2>Le Nostre Sezioni</h2>
    <p>Scegli l'area tecnologica di tuo interesse</p>
</div>

{{< cards >}}
  {{< card link="/docs/proxmox" title="Proxmox Homelab" icon="server" subtitle="Guide sulla virtualizzazione e gestione server domestici." >}}
  {{< card link="/docs/raspberry-pi" title="Mondo Raspberry" icon="cpu-chip" subtitle="Progetti creativi e soluzioni per la tua board preferita." >}}
  {{< card link="/docs/linux" title="Cultura Linux" icon="command-line" subtitle="Recensioni distro, tutorial terminale e filosofia open source." >}}
{{< /cards >}}

<div id="articoli" class="section-title">
    <h2>Ultimi Articoli</h2>
    <p>Le novità pubblicate recentemente su TuxPi</p>
</div>

<!-- Sezione Articoli Dinamica -->
{{< latest-articles >}}

</div>

<script>
const phrases = ["Linux & Raspberry Pi", "Proxmox Homelab", "Virtualizzazione & Libertà"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0; let charIndex = 0; let isDeleting = false; let typeSpeed = 100;

function updateSlides(index) {
    slides.forEach((slide, i) => {
        slide.classList.remove('active');
        if (i === index) slide.classList.add('active');
    });
}

function typeEffect() {
    const currentPhrase = phrases[currentIndex];
    if (isDeleting) {
        textElement.textContent = currentPhrase.substring(0, charIndex - 1);
        charIndex--; typeSpeed = 40; 
    } else {
        textElement.textContent = currentPhrase.substring(0, charIndex + 1);
        charIndex++; typeSpeed = 120;
    }
    if (!isDeleting && charIndex === currentPhrase.length) {
        isDeleting = true; typeSpeed = 3000; 
    } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        currentIndex = (currentIndex + 1) % phrases.length;
        updateSlides(currentIndex);
        typeSpeed = 500; 
    }
    setTimeout(typeEffect, typeSpeed);
}
document.addEventListener('DOMContentLoaded', typeEffect);
</script>

<style>
/* --- HERO STYLE --- */
.tuxpi-hero-container {
    position: relative; width: 100vw; height: 95vh;
    left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw;
    margin-top: -3.5rem; overflow: hidden; background: #000;
}
.hero-slide {
    position: absolute; inset: 0; background-size: cover; background-position: center;
    opacity: 0; transform: scale(1.1); transition: opacity 1.5s ease-in-out, transform 6s ease-in-out;
}
.hero-slide.active { opacity: 1; transform: scale(1); z-index: 2; }
.hero-overlay {
    position: relative; z-index: 10; height: 100%; display: flex;
    align-items: center; justify-content: center; background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.5) 90%);
}
.hero-title { font-size: clamp(5rem, 20vw, 12rem) !important; font-weight: 900 !important; letter-spacing: -8px; color: white !important; }
.hero-title span { color: #3b82f6; }
.typing-container { margin-top: 2rem; height: 3.5rem; font-family: monospace; font-size: clamp(1.2rem, 4vw, 2.5rem); color: #cbd5e1; }
.cursor { animation: blink 0.8s infinite; color: #3b82f6; font-weight: bold; }
@keyframes blink { 50% { opacity: 0; } }
.hero-buttons { margin-top: 4rem; display: flex; gap: 20px; }
.btn { padding: 16px 40px; border-radius: 50px; font-weight: 800; text-decoration: none; text-transform: uppercase; transition: 0.4s; }
.btn-blue { background: #3b82f6; color: white; }
.btn-outline { border: 2px solid white; color: white; }

/* --- CONTENT STYLE --- */
.home-content-wrapper { padding: 4rem 0; }
.section-title { text-align: center; margin: 4rem 0 2rem 0; }
.section-title h2 { font-size: 2.5rem !important; color: #3b82f6 !important; }
.section-title p { color: #94a3b8; font-size: 1.1rem; }

/* PULIZIA HEXTRA */
.hextra-breadcrumb, .next-link, .prev-link, .mt-16, footer { display: none !important; }
</style>
