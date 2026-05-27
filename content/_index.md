---
title: "TuxPi: Linux, Raspberry Pi & Proxmox"
---

<!-- SEZIONE HERO CON IMMAGINE E TESTO ANIMATO -->
<div class="relative w-full h-[500px] flex items-center justify-center overflow-hidden rounded-2xl shadow-xl mb-12">
  
  <!-- Immagine di sfondo tech -->
  <div class="absolute inset-0 z-0">
    <img src="https://images.unsplash.com/photo-1518770660439-4636190af475?q=80&w=2070" 
         class="w-full h-full object-cover brightness-[0.4]" 
         alt="TuxPi Tech Background">
  </div>

  <!-- Contenuto Testuale -->
  <div class="relative z-10 text-center px-6">
    <h1 class="text-5xl md:text-7xl font-extrabold text-white mb-6 tracking-tight">
      Progetto <span class="text-blue-400">TuxPi</span>
    </h1>
    
    <!-- Testo Animato (Typing Effect) -->
    <div class="h-10">
      <p class="text-xl md:text-3xl font-mono text-gray-200 inline-block">
        > <span class="typing-animation"></span><span class="cursor-blink">|</span>
      </p>
    </div>

    <div class="mt-10 flex justify-center gap-4">
      <a href="/blog/" class="bg-blue-600 hover:bg-blue-500 text-white font-bold py-3 px-8 rounded-full transition-all transform hover:scale-105">
        Leggi il Blog
      </a>
      <a href="/docs/" class="bg-transparent border-2 border-white/50 hover:border-white text-white font-bold py-3 px-8 rounded-full transition-all">
        Documentazione
      </a>
    </div>
  </div>
</div>

<style>
/* Animazione della scritta che cambia */
.typing-animation::after {
  content: "";
  animation: changeText 10s infinite;
}

@keyframes changeText {
  0%, 25% { content: "Linux per tutti"; }
  26%, 50% { content: "Raspberry Pi & Homelab"; }
  51%, 75% { content: "Proxmox Virtualizzazione"; }
  76%, 100% { content: "Software Libero"; }
}

/* Cursore che lampeggia */
.cursor-blink {
  animation: blink 0.8s infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}
</style>

---

## 📂 Esplora il progetto
Scopri le nostre guide dettagliate e gli ultimi aggiornamenti dal mondo TuxPi.

{{< cards >}}
  {{< card link="/blog/" title="Ultimi Articoli" icon="book-open" subtitle="Guide, recensioni e news su Linux." >}}
  {{< card link="/docs/proxmox/" title="Proxmox Guide" icon="cog" subtitle="Configura il tuo server domestico." >}}
  {{< card link="/docs/raspberry-pi/" title="Mondo Raspberry" icon="terminal" subtitle="Progetti creativi con la single board." >}}
{{< /cards >}}

---

### 🚀 Perché Linux?
L'obiettivo di **TuxPi** è mostrare come il software libero possa ridare vita a vecchi PC (addio Windows 10!) e offrire un ambiente di sviluppo sicuro e potente. 

[Scopri di più sulla nostra missione →](/chi-sono/)
