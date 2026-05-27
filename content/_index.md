<div class="tuxpi-hero-container">
    <div id="hero-slider" class="hero-slider">
        <div class="hero-slide active" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://github.com/Tux-Pi/tuxpi.github.io/blob/b02196d5ad98d9462049559481e92fddba6e0318/images/ChatGPT%20Image%2021%20dic%202025%2C%2011_52_37.png');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070');"></div>
        <div class="hero-slide" style="background-image: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1558494949-ef010cbdcc51?q=80&w=2000');"></div>
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
                <a href="#articoli" class="btn btn-blue">Articoli</a>
                <a href="#sezioni" class="btn btn-outline">Sezioni</a>
            </div>
        </div>
    </div>
</div>

<div class="home-content-wrapper">

# 🐧 Benvenuto su TuxPi
In questo blog esploriamo la tecnologia **Linux**, con un focus particolare sul **Software Libero** e la virtualizzazione con **Proxmox**.

<div id="sezioni" class="section-title">
    <h2>Le Nostre Sezioni</h2>
</div>

{{< cards >}}
  {{< card link="/docs/proxmox" title="Proxmox Lab" icon="server" subtitle="Gestione server e virtualizzazione." >}}
  {{< card link="/docs/raspberry-pi" title="Mondo Raspberry" icon="terminal" subtitle="Progetti creativi con la board Pi." >}}
  {{< card link="/docs/linux" title="Cultura Linux" icon="book-open" subtitle="Recensioni e tutorial Open Source." >}}
{{< /cards >}}

<div id="articoli" class="section-title">
    <h2>Ultimi Articoli</h2>
</div>

{{< latest-articles >}}

</div>

<script>
const phrases = ["Linux & Raspberry Pi", "Proxmox Homelab", "Virtualizzazione & Libertà"];
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
</script>

<style>
.tuxpi-hero-container { position: relative; width: 100vw; height: 95vh; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; margin-top: -3.5rem; overflow: hidden; background: #000; }
.hero-slide { position: absolute; inset: 0; background-size: cover; background-position: center; opacity: 0; transform: scale(1.1); transition: opacity 1.5s ease, transform 6s ease; }
.hero-slide.active { opacity: 1; transform: scale(1); z-index: 2; }
.hero-overlay { position: relative; z-index: 10; height: 100%; display: flex; align-items: center; justify-content: center; background: radial-gradient(circle, transparent, rgba(0,0,0,0.5)); }
.hero-title { font-size: clamp(5rem, 20vw, 12rem) !important; font-weight: 900 !important; color: white !important; margin: 0 !important; letter-spacing: -8px; }
.hero-title span { color: #3b82f6; }
.typing-container { margin-top: 1rem; height: 3rem; font-family: monospace; font-size: clamp(1.2rem, 4vw, 2.5rem); color: #cbd5e1; }
.cursor { animation: blink 0.8s infinite; color: #3b82f6; }
@keyframes blink { 50% { opacity: 0; } }
.hero-buttons { margin-top: 3rem; display: flex; gap: 15px; }
.btn { padding: 15px 35px; border-radius: 50px; font-weight: bold; text-decoration: none; text-transform: uppercase; transition: 0.3s; }
.btn-blue { background: #3b82f6; color: white; }
.btn-outline { border: 2px solid white; color: white; }
.home-content-wrapper { max-width: 1200px; margin: 0 auto; padding: 2rem; }
.section-title { text-align: center; margin-top: 4rem; }
.hextra-breadcrumb, .next-link, .prev-link, footer { display: none !important; }
</style>
