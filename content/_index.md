<div class="tuxpi-hero-container">
    <div id="hero-slider" class="hero-slider">
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
    </div>
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
                <a href="#sezioni" class="btn btn-outline">Sezioni Tech</a>
            </div>
        </div>
    </div>
    <!-- Sfumatura verso il basso per unire lo slider al contenuto -->
    <div class="hero-bottom-gradient"></div>
</div>

<div class="home-content-wrapper">

<div class="intro-box">

# 🐧 Benvenuto su TuxPi
In questo blog si parla di tecnologia legata al mondo Linux, con un’attenzione particolare ai vantaggi che il sistema operativo del pinguino offre rispetto ad altri ambienti.
Troverai articoli di approfondimento, guide pratiche e recensioni su distribuzioni, software open source, strumenti di sviluppo e soluzioni per ottimizzare l’esperienza d’uso.
L’obiettivo è diffondere la cultura Linux e del software libero, aiutando utenti di ogni livello a scoprire un modo più libero, sicuro e personalizzabile di vivere la tecnologia.

</div>

<div id="sezioni" class="section-container">
    <div class="section-header">
        <span class="section-tag">Esplora</span>
        <h2 class="section-title">Le Nostre Sezioni</h2>
    </div>

{{< cards >}}
  {{< card link="/docs/proxmox" title="Proxmox Lab" icon="server" subtitle="Ottimizzazione e gestione nodi." >}}
  {{< card link="/docs/raspberry-pi" title="Mondo Raspberry" icon="terminal" subtitle="Progetti hardware e software." >}}
  {{< card link="/docs/linux" title="Cultura Linux" icon="book-open" subtitle="Recensioni e tutorial Open Source." >}}
{{< /cards >}}

</div>

<div id="articoli" class="section-container">
    <div class="section-header">
        <span class="section-tag">News</span>
        <h2 class="section-title">Ultimi Articoli</h2>
    </div>

{{< latest-articles >}}

</div>

</div>

<script>
// Sincronizzazione Slider e Scrittura
const phrases = ["Linux & Open Source", "Proxmox Homelab", "Raspberry Pi & IoT"];
const slides = document.querySelectorAll('.hero-slide');
const textElement = document.getElementById('typing-text');
let currentIndex = 0, charIndex = 0, isDeleting = false, typeSpeed = 100;

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

// Smooth Scrolling per i pulsanti
document.querySelectorAll('a[href^="#"]').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        document.querySelector(this.getAttribute('href')).scrollIntoView({
            behavior: 'smooth'
        });
    });
});
</script>

<style>
/* --- HERO REFINEMENT --- */
.tuxpi-hero-container { position: relative; width: 100vw; height: 95vh; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; margin-top: -3.5rem; overflow: hidden; background: #000; }
.hero-slide { position: absolute; inset: 0; background-size: cover; background-position: center; opacity: 0; transform: scale(1.1); transition: opacity 1.5s ease, transform 10s linear; }
.hero-slide.active { opacity: 1; transform: scale(1.02); z-index: 2; }
.hero-overlay { position: relative; z-index: 10; height: 100%; display: flex; align-items: center; justify-content: center; background: radial-gradient(circle, transparent 20%, rgba(0,0,0,0.6) 90%); }
.hero-bottom-gradient { position: absolute; bottom: 0; width: 100%; height: 200px; background: linear-gradient(to top, #111 0%, transparent 100%); z-index: 11; }

.hero-title { font-size: clamp(5rem, 20vw, 12rem) !important; font-weight: 900 !important; color: white !important; margin: 0 !important; letter-spacing: -8px; text-shadow: 0 10px 30px rgba(0,0,0,0.5); }
.hero-title span { color: #3b82f6; text-shadow: 0 0 50px rgba(59, 130, 246, 0.4); }

.typing-container { margin-top: 1rem; height: 3rem; font-family: 'JetBrains Mono', monospace; font-size: clamp(1.2rem, 4vw, 2.5rem); color: #cbd5e1; }
.cursor { animation: blink 0.8s infinite; color: #3b82f6; font-weight: bold; }
@keyframes blink { 50% { opacity: 0; } }

.hero-buttons { margin-top: 4rem; display: flex; gap: 20px; }
.btn { padding: 15px 35px; border-radius: 12px; font-weight: bold; text-decoration: none !important; text-transform: uppercase; transition: 0.3s cubic-bezier(0.4, 0, 0.2, 1); font-size: 0.9rem; letter-spacing: 1px; }
.btn-blue { background: #3b82f6; color: white; border: 1px solid #3b82f6; }
.btn-blue:hover { background: #2563eb; transform: translateY(-3px); box-shadow: 0 10px 20px rgba(59, 130, 246, 0.3); }
.btn-outline { border: 1px solid rgba(255,255,255,0.4); color: white; backdrop-filter: blur(5px); }
.btn-outline:hover { border-color: white; background: rgba(255,255,255,0.1); transform: translateY(-3px); }

/* --- CONTENT REFINEMENT --- */
.home-content-wrapper { max-width: 1200px; margin: 0 auto; padding: 0 2rem 5rem 2rem; background: transparent; }

.intro-box { text-align: center; padding: 5rem 0; border-bottom: 1px solid rgba(255,255,255,0.05); }
.intro-box h1 { font-size: 3rem !important; margin-bottom: 1.5rem !important; font-weight: 800 !important; }

.section-container { padding: 6rem 0 2rem 0; }
.section-header { text-align: center; margin-bottom: 3rem; }
.section-tag { background: rgba(59, 130, 246, 0.1); color: #3b82f6; padding: 5px 15px; border-radius: 20px; font-size: 0.8rem; font-weight: bold; text-transform: uppercase; letter-spacing: 2px; }
.section-title h2 { font-size: 2.8rem !important; font-weight: 800 !important; margin-top: 10px !important; }

/* Adattamento Carte Hextra */
.hx-card { transition: all 0.3s ease !important; border: 1px solid rgba(255,255,255,0.05) !important; background: rgba(255,255,255,0.02) !important; }
.hx-card:hover { transform: translateY(-10px) !important; border-color: rgba(59, 130, 246, 0.4) !important; background: rgba(59, 130, 246, 0.05) !important; }

/* NASCONDE ELEMENTI INUTILI */
.hextra-breadcrumb, .next-link, .prev-link, .mt-16, footer .mx-auto { display: none !important; }
</style>
