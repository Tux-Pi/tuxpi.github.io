---
title: "TuxPi - Home"
---

<!-- 1. BLOCCO HERO GIGANTE (Breakout) -->
<div class="breakout-section hero-section">
  <div class="hero-content">
    <div class="glass-box">
        <span class="badge">🚀 Benvenuti nel futuro Open Source</span>
        <h1 class="main-title">TUX<span>PI</span></h1>
        <div class="dynamic-subtitle">> <span class="typing"></span><span class="cursor">_</span></div>
        <div class="hero-actions">
            <a href="/blog" class="btn btn-blue">Esplora Articoli</a>
            <a href="/docs" class="btn btn-outline">Sezioni Tecniche</a>
        </div>
    </div>
  </div>
</div>

<!-- 2. BLOCCO "PERCHÈ TUXPI?" (Tre colonne chiare) -->
<div class="info-section">
    <div class="info-grid">
        <div class="info-card">
            <div class="info-icon">🐧</div>
            <h3>Linux Power</h3>
            <p>Scopri come passare a Linux e dire addio alle restrizioni di Windows 10/11.</p>
        </div>
        <div class="info-card">
            <div class="info-icon">🥧</div>
            <h3>Raspberry Pi</h3>
            <p>Guide passo-passo per trasformare una piccola scheda in un server potente.</p>
        </div>
        <div class="info-card">
            <div class="info-icon">☁️</div>
            <h3>Virtualizzazione</h3>
            <p>Domina Proxmox per creare il tuo Cloud privato e sicuro a casa tua.</p>
        </div>
    </div>
</div>

<!-- 3. SEZIONE CONTENUTI PRINCIPALI -->
<div class="breakout-section categories-section">
    <div class="category-banner">
        <div class="category-text">
            <h2>Proxmox Homelab</h2>
            <p>Tutto quello che devi sapere per gestire il tuo nodo Proxmox, container LxC e macchine virtuali.</p>
            <a href="/docs/proxmox" class="link-btn">Vai alla sezione →</a>
        </div>
        <div class="category-image">
            <img src="https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000" alt="Server">
        </div>
    </div>
</div>

<style>
/* --- SETUP STRUTTURA GIGANTE --- */
:root {
    --primary-blue: #3b82f6;
    --dark-bg: #0f172a;
}

.breakout-section {
    width: 100vw;
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
}

/* --- HERO SECTION --- */
.hero-section {
    height: 90vh;
    min-height: 600px;
    background: url('https://images.unsplash.com/photo-1550751827-4bd374c3f58b?q=80&w=2070') no-repeat center center;
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: -2rem;
}

.glass-box {
    background: rgba(15, 23, 42, 0.7);
    backdrop-filter: blur(12px);
    border: 1px solid rgba(255, 255, 255, 0.1);
    padding: 3rem;
    border-radius: 2rem;
    text-align: center;
    max-width: 800px;
    box-shadow: 0 25px 50px -12px rgba(0, 0, 0, 0.5);
}

.main-title {
    font-size: clamp(4rem, 12vw, 8rem) !important;
    font-weight: 900 !important;
    color: white !important;
    margin: 0 !important;
    line-height: 1;
    letter-spacing: -4px;
}

.main-title span { color: var(--primary-blue); }

.dynamic-subtitle {
    font-family: 'Courier New', monospace;
    font-size: 1.5rem;
    color: #94a3b8;
    margin-top: 1rem;
}

.typing::after {
    content: "";
    animation: type 10s infinite;
}

@keyframes type {
    0%, 25% { content: "Il blog di TuxMaker"; }
    26%, 50% { content: "Linux & Raspberry Pi"; }
    51%, 75% { content: "Proxmox & Homelab"; }
    76%, 100% { content: "Addio Windows 10!"; }
}

/* --- INFO CARDS --- */
.info-section {
    padding: 6rem 0;
}

.info-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
}

.info-card {
    background: #1e293b;
    padding: 2.5rem;
    border-radius: 1.5rem;
    text-align: center;
    transition: 0.3s ease;
    border-bottom: 4px solid transparent;
}

.info-card:hover {
    transform: translateY(-10px);
    border-color: var(--primary-blue);
}

.info-icon { font-size: 3rem; margin-bottom: 1rem; }

/* --- CATEGORY BANNER --- */
.categories-section {
    background: #1e293b;
    padding: 4rem 0;
}

.category-banner {
    max-width: 1200px;
    margin: 0 auto;
    display: flex;
    align-items: center;
    gap: 4rem;
    padding: 0 2rem;
}

.category-text h2 { font-size: 3rem !important; color: white !important; margin-bottom: 1rem !important;}
.category-text p { font-size: 1.2rem; color: #94a3b8; margin-bottom: 2rem; }

.category-image img {
    border-radius: 2rem;
    width: 500px;
    box-shadow: 0 20px 40px rgba(0,0,0,0.4);
}

/* --- BOTTONI --- */
.btn {
    padding: 1rem 2.5rem;
    border-radius: 50px;
    font-weight: 700;
    text-decoration: none;
    display: inline-block;
    transition: 0.3s;
    margin: 0.5rem;
}

.btn-blue { background: var(--primary-blue); color: white; }
.btn-outline { border: 2px solid white; color: white; }
.btn:hover { opacity: 0.8; transform: scale(1.05); }

.link-btn {
    color: var(--primary-blue);
    font-weight: 700;
    text-decoration: none;
    font-size: 1.1rem;
}

@media (max-width: 768px) {
    .category-banner { flex-direction: column; text-align: center; }
    .category-image img { width: 100%; }
}
</style>
