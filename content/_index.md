<div class="tuxpi-hero-container">
    <div id="hero-slider" class="hero-slider">
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.8)), url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/proxmox-homelab.png');"></div>
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
                <a href="#sezioni" class="btn btn-outline">Sezioni</a>
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
        <span class="section-tag">Esplora l'ecosistema</span>
        <h2 class="section-title">Domina il tuo Hardware</h2>
    </div>

<div class="tuxpi-cards-grid">
        <!-- CARD 1: PROXMOX -->
        <a href="/docs/proxmox" class="tux-card">
            <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=800');"></div>
            <div class="card-content">
                <div class="card-icon">🖥️</div>
                <h3>Proxmox Lab</h3>
                <p>Virtualizzazione estrema. Gestisci i tuoi nodi e crea un datacenter domestico professionale.</p>
            </div>
        </a>

<!-- CARD 2: RASPBERRY PI -->
<a href="/docs/raspberry-pi" class="tux-card">
            <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1629739945244-c7821487b257?q=80&w=800');"></div>
            <div class="card-content">
                <div class="card-icon">🥧</div>
                <h3>Mondo Raspberry</h3>
                <p>Dallo sviluppo IoT ai server a basso consumo. Progetti pratici per la single-board più amata.</p>
            </div>
        </a>

<a href="/docs/self-hosting" class="tux-card">
            <div class="card-bg" style="background-image: url('https://images.unsplash.com/photo-1605745341112-85968b193ef5?q=80&w=800');"></div>
            <div class="card-content">
                <div class="card-icon">🐳</div>
                <h3>Self-Hosting</h3>
                <p>Docker, Portainer e servizi Cloud privati. Prendi il controllo dei tuoi dati senza dipendere da terzi.</p>
            </div>
        </a>
        <!-- CARD 4: CULTURA LINUX -->
        <a href="/docs/linux" class="tux-card">
            <div class="card-bg" style="background-image: url('https://raw.githubusercontent.com/Tux-Pi/tuxpi.github.io/main/images/linux-opensource.png');"></div>
            <div class="card-content">
                <div class="card-icon">🐧</div>
                <h3>Cultura Linux</h3>
                <p>Filosofia Open Source, guide al terminale e recensioni delle migliori distribuzioni del pinguino.</p>
            </div>
        </a>
    </div>
</div>

</div>

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

/* --- TRASFORMAZIONE CARD TUXPI --- */

/* 1. Il contenitore delle card */
.hextra-cards {
    gap: 2rem !important;
    margin-top: 2rem !important;
}

/* 2. Stile della singola Card */
.hx-card {
    background: rgba(255, 255, 255, 0.03) !important; /* Effetto vetro scuro */
    backdrop-filter: blur(10px) !important;
    border: 1px solid rgba(255, 255, 255, 0.08) !important;
    border-radius: 20px !important;
    padding: 1.5rem !important;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275) !important;
    position: relative;
    overflow: hidden;
}

/* 3. Effetto Hover (Elevazione e Luce) */
.hx-card:hover {
    transform: translateY(-12px) scale(1.02) !important;
    background: rgba(59, 130, 246, 0.08) !important; /* Bagliore blu soft */
    border-color: rgba(59, 130, 246, 0.5) !important;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4), 
                0 0 20px rgba(59, 130, 246, 0.2) !important;
}

/* 4. Animazione Icona */
.hx-card svg {
    color: #3b82f6 !important; /* Colore blu TuxPi */
    width: 2.5rem !important;
    height: 2.5rem !important;
    transition: transform 0.5s ease !important;
    filter: drop-shadow(0 0 8px rgba(59, 130, 246, 0.4));
}

.hx-card:hover svg {
    transform: rotate(-10deg) scale(1.2) !important;
    color: #60a5fa !important;
}

/* 5. Titolo e Sottotitolo */
.hx-card h3 {
    font-size: 1.5rem !important;
    font-weight: 700 !important;
    margin-top: 1rem !important;
    color: white !important;
    letter-spacing: -0.5px;
}

.hx-card p {
    color: #94a3b8 !important;
    line-height: 1.5 !important;
    margin-top: 0.5rem !important;
    font-size: 0.95rem !important;
}

/* 6. Decorazione extra: linea luminosa in alto al passaggio del mouse */
.hx-card::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(90deg, transparent, #3b82f6, transparent);
    transform: translateX(-100%);
    transition: transform 0.6s;
}

.hx-card:hover::before {
    transform: translateX(100%);
}

/* GRIGLIA A 4 COLONNE */
.tuxpi-cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 25px;
    margin-top: 40px;
    padding: 0 10px;
}

/* LA CARD INDIVIDUALE */
.tux-card {
    position: relative;
    height: 320px;
    border-radius: 24px;
    overflow: hidden;
    display: flex;
    align-items: flex-end;
    text-decoration: none !important;
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
}

/* L'IMMAGINE DI SFONDO DELLA CARD */
.card-bg {
    position: absolute;
    inset: 0;
    background-size: cover;
    background-position: center;
    filter: brightness(0.4) grayscale(0.2); /* Scura di base */
    transition: all 0.6s ease;
    z-index: 1;
}

/* CONTENUTO SOPRA L'IMMAGINE */
.card-content {
    position: relative;
    z-index: 2;
    padding: 30px;
    width: 100%;
    background: linear-gradient(to top, rgba(0,0,0,0.9) 0%, transparent 100%);
    transition: all 0.4s ease;
}

.card-icon {
    font-size: 2.5rem;
    margin-bottom: 15px;
    transform: translateY(10px);
    transition: all 0.4s ease;
}

.tux-card h3 {
    color: #fff !important;
    font-size: 1.6rem !important;
    font-weight: 800 !important;
    margin: 0 0 10px 0 !important;
    text-shadow: 0 2px 10px rgba(0,0,0,0.5);
}

.tux-card p {
    color: #cbd5e1 !important;
    font-size: 0.95rem !important;
    line-height: 1.5 !important;
    opacity: 0.8;
    margin: 0 !important;
}

/* EFFETTI HOVER (QUANDO PASSI IL MOUSE) */
.tux-card:hover {
    transform: translateY(-15px);
    border-color: #3b82f6;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.6), 0 0 20px rgba(59, 130, 246, 0.3);
}

.tux-card:hover .card-bg {
    filter: brightness(0.6) grayscale(0); /* Si schiarisce e prende colore */
    transform: scale(1.1); /* Effetto zoom */
}

.tux-card:hover .card-icon {
    transform: translateY(0) scale(1.2);
}

.tux-card:hover .card-content {
    background: linear-gradient(to top, rgba(59, 130, 246, 0.3) 0%, transparent 100%);
}

@media (max-width: 768px) {
    .tuxpi-cards-grid { grid-template-columns: 1fr; }
    .tux-card { height: 280px; }
}
</style>
