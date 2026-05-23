---
title: TuxPi - Il mondo Linux nelle tue mani
---

<div class="relative preserve-3d h-[500px] w-full mb-12 rounded-xl overflow-hidden shadow-2xl">
  <!-- Immagine di Sfondo con Overlay scuro -->
  <div class="absolute inset-0 bg-cover bg-center z-0" style="background-image: url('/images/hero-bg.jpg');">
    <div class="absolute inset-0 bg-black/60"></div>
  </div>

  <!-- Contenuto dello Slider/Hero -->
  <div class="relative z-10 flex flex-col items-center justify-center h-full text-center px-4">
    <h1 class="text-4xl md:text-6xl font-bold text-white mb-4">
      Progetto <span class="text-blue-400">TuxPi</span>
    </h1>
    
    <!-- Testo che si muove (Typing Effect) -->
    <p class="text-xl md:text-2xl text-gray-200 font-mono">
      > <span class="typing-text"></span><span class="cursor">|</span>
    </p>

    <div class="mt-8 flex gap-4">
      <a href="/blog/" class="bg-blue-600 hover:bg-blue-700 text-white px-6 py-3 rounded-lg font-bold transition">Esplora Articoli</a>
      <a href="#sezioni" class="bg-white/10 hover:bg-white/20 text-white border border-white/30 px-6 py-3 rounded-lg font-bold transition">Scopri Sezioni</a>
    </div>
  </div>
</div>

<style>
/* Animazione Typing */
.typing-text::after {
  content: "Linux per tutti";
  animation: typing 8s infinite;
}

@keyframes typing {
  0%, 20% { content: "Linux per tutti"; }
  25%, 45% { content: "Raspberry Pi & Proxmox"; }
  50%, 70% { content: "Open Source Power"; }
  75%, 95% { content: "Benvenuti su TuxPi"; }
}

.cursor {
  animation: blink 1s infinite;
}

@keyframes blink {
  50% { opacity: 0; }
}
</style>

<div id="sezioni"></div>

## Esplora le risorse
{{< cards >}}
  {{< card link="/blog/" title="Leggi gli Articoli" icon="book-open" >}}
  {{< card link="/docs/proxmox/" title="Proxmox Homelab" icon="cog" >}}
  {{< card link="/docs/raspberry-pi/" title="Mondo Raspberry" icon="terminal" >}}
{{< /cards >}}
