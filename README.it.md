# KeepAwake

**[English](README.md) · [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Español](README.es.md) · [Français](README.fr.md) · [Deutsch](README.de.md) · [Português](README.pt-BR.md) · [Italiano](README.it.md)**

Un'app per la barra dei menu di macOS che controlla il comportamento di sospensione del MacBook con due interruttori indipendenti — mantiene il tuo Mac sveglio a coperchio chiuso e blocca la sospensione da inattività mentre lavori.

> 📦 **Questo repository distribuisce solo il `.dmg` firmato e notarizzato. Il codice sorgente si trova in un repository privato.**

## ⬇️ Download

Ultima versione → **[KeepAwake-releases/releases/latest](../../releases/latest)**

Ogni `.dmg` è firmato con Developer ID `C3SNXE45AV (Xiaoneng Wu)` e notarizzato da Apple. Il Gatekeeper di macOS lo accetta senza mostrare il secondo dialogo di conferma "scaricato da internet".

## 🧰 Requisiti di sistema

- macOS 14 Sonoma o successivo
- Apple Silicon o Intel

## ✨ Funzionalità

- **Sveglio a coperchio chiuso** — mantiene il Mac in funzione anche a coperchio chiuso (richiede autorizzazione amministratore la prima volta)
- **Impedire sospensione da inattività** — sopprime la sospensione innescata da inattività mentre KeepAwake è in esecuzione (IOKit assertion)
- **Timer di spegnimento automatico** — 30 min / 1 / 2 / 4 / 8 ore
- **Avvio automatico al login, ricorda ultimo stato, ripristino automatico degli interruttori alla chiusura**
- **Sicuro in caso di crash** — se l'app si blocca, l'helper ripristina `disablesleep` a 0 dopo 60 s
- **15 lingue** — segue la lingua di sistema di macOS

## 📥 Installazione

1. Scarica `KeepAwake-0.2.0.dmg` dalla [ultima versione](../../releases/latest)
2. Doppio clic sul DMG per montarlo, trascina **KeepAwake.app** in `/Applications`
3. Avvia da Launchpad o dalla cartella Applicazioni
4. Al primo attivamento di "Sveglio a coperchio chiuso", macOS chiederà il permesso di aggiungere un elemento in background → clicca **Consenti**

## 🔐 Firma e notarizzazione

- Developer ID: `Xiaoneng Wu (C3SNXE45AV)`
- Servizio di notarizzazione Apple: ✅ Accettato
- Ticket pinzato (funziona offline, il Gatekeeper può verificare senza rete)

## ⚠️ Rischio di surriscaldamento a coperchio chiuso — leggi

**La principale ventola di dissipazione del MacBook si trova sotto la tastiera.** Quando il coperchio è chiuso e il portatile è appoggiato piatto su una superficie, il flusso d'aria è ridotto. Eseguire carichi pesanti in questo stato (export video, compilazioni, training ML, inferenza AI prolungata, giochi) può causare:

- Thermal throttling di CPU/GPU → il tuo compito in realtà diventa *più lento*
- Invecchiamento accelerato della batteria per temperature alte prolungate
- Nei casi estremi, spegnimento termico o danni hardware

**Uso sicuro:**

- ✅ Adatto a compiti **leggeri** in background — sincronizzazione file, download, mantenere SSH / desktop remoto, ricezione AirPlay
- ⚠️ Per carichi **pesanti** a coperchio chiuso, solleva il portatile o usa un supporto con ventilazione. **Non** posizionarlo su letto, coperta, divano, o dentro una borsa.
- ❌ Non combinare "coperchio chiuso + carico pesante + ventole ostruite"

`Impedire sospensione da inattività` sovrascrive anche il risparmio energetico. Attivalo quando serve, disattivalo quando non serve più.

**KeepAwake non monitora temperatura né carico. La gestione del rischio è a carico tuo.**

## 🔒 Riguardo al codice sorgente

Il repository sorgente è privato. Questo repository esiste solo per distribuire il DMG firmato e notarizzato. Se hai bisogno di accesso al codice per audit o contributi, contatta l'autore.

## Licenza

Uso personale.
