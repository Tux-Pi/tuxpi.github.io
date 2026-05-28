
<!-- HEADER DELLA PAGINA CHI SONO -->
<div class="about-hero">
    <div class="about-hero-content">
        <span class="badge">L'anima del progetto</span>
        <h1>Dietro le quinte di <span class="blue-text">TuxPi</span></h1>
        <p>Passione per l'Open Source, curiosità per l'hardware e una missione: la libertà digitale.</p>
    </div>
</div>

<div class="about-wrapper">

## 🐧 Chi è TuxMaker?

Ciao! Mi chiamo **TuxMaker**, l'ideatore e curatore di questo spazio. 

Il progetto **TuxPi** è nato originariamente su `tuxpi.ddns.net` come un piccolo esperimento domestico su un Raspberry Pi. Con il tempo, la passione per il mondo **Linux** e l'esigenza di avere il controllo totale sui miei dati mi hanno spinto a esplorare orizzonti più ampi: dalla virtualizzazione con **Proxmox** al **self-hosting** massivo tramite Docker.

> "Non si tratta solo di installare software, ma di capire come riprendersi la proprietà della propria vita digitale."

---

## 🛠️ Il mio "Garage" Digitale (Homelab)

Molti mi chiedono cosa faccia girare TuxPi. Ecco una panoramica dell'hardware e delle tecnologie che utilizzo quotidianamente e di cui parlo nei miei articoli:

<div class="tech-grid">
    <div class="tech-item">
        <strong>Server Principale</strong>
        <p>Nodo Proxmox su hardware x86 per virtualizzazione pesante.</p>
    </div>
    <div class="tech-item">
        <strong>Edge Computing</strong>
        <p>Cluster di Raspberry Pi 4 e 5 per servizi h24 a basso consumo.</p>
    </div>
    <div class="tech-item">
        <strong>Storage</strong>
        <p>Soluzioni NAS custom per backup e gestione file multimediali.</p>
    </div>
    <div class="tech-item">
        <strong>Containerizzazione</strong>
        <p>Oltre 30 servizi Docker gestiti tramite Portainer e traefik.</p>
    </div>
</div>

---

## 🚀 La Missione di TuxPi

Questo sito non è solo un manuale tecnico. È una testimonianza di come la tecnologia possa essere accessibile e divertente. Attraverso questo blog voglio:

1.  **Divulgare la cultura Linux**: Dimostrare che esiste un'alternativa valida (e migliore) ai sistemi proprietari.
2.  **Supportare la Community**: Condividere configurazioni e script che mi hanno salvato ore di lavoro.
3.  **Promuovere il Riciclo Tech**: Far capire come un vecchio PC o una scheda da 40€ possano diventare più potenti di un servizio cloud costoso.

Se vuoi scambiare due chiacchiere o hai domande sui miei progetti, non esitare a [contattarmi](/contatti)!

</div>

<style>
/* --- STILE PAGINA CHI SONO --- */

.about-hero {
    width: 100vw;
    position: relative;
    left: 50%;
    right: 50%;
    margin-left: -50vw;
    margin-right: -50vw;
    background: linear-gradient(rgba(15, 23, 42, 0.9), rgba(15, 23, 42, 0.9)), 
                url('https://images.unsplash.com/photo-1510511459019-5dee997dd1db?q=80&w=2000');
    background-size: cover;
    background-position: center;
    padding: 6rem 1rem;
    text-align: center;
    margin-top: -2rem;
    border-bottom: 1px solid rgba(59, 130, 246, 0.2);
}

.about-hero-content h1 {
    font-size: clamp(2.5rem, 6vw, 4rem) !important;
    font-weight: 800 !important;
    color: white !important;
    margin-top: 1rem !important;
}

.badge {
    background: rgba(59, 130, 246, 0.2);
    color: #3b82f6;
    padding: 5px 15px;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 2px;
}

.blue-text { color: #3b82f6; }

.about-wrapper {
    max-width: 900px;
    margin: 0 auto;
    padding: 4rem 1.5rem;
    line-height: 1.8;
}

/* Griglia Tech */
.tech-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1.5rem;
    margin: 2rem 0;
}

.tech-item {
    background: rgba(255, 255, 255, 0.03);
    padding: 1.5rem;
    border-radius: 15px;
    border-left: 3px solid #3b82f6;
    transition: transform 0.3s ease;
}

.tech-item:hover {
    transform: translateX(5px);
    background: rgba(59, 130, 246, 0.05);
}

.tech-item strong {
    display: block;
    color: #3b82f6;
    margin-bottom: 0.5rem;
}

.tech-item p {
    font-size: 0.9rem;
    margin: 0;
    color: #94a3b8;
}

/* Citazione */
blockquote {
    border-left: 4px solid #3b82f6 !important;
    background: rgba(59, 130, 246, 0.05);
    padding: 1.5rem !important;
    font-style: italic;
    border-radius: 0 15px 15px 0;
    margin: 2rem 0 !important;
}

hr {
    opacity: 0.1;
    margin: 3rem 0;
}
</style>
