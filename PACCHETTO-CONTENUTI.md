# PACCHETTO CONTENUTI — Landing Page Estro Agency (PMI)

> Documento di hand-off per lo sviluppo. Contiene tutti i testi, gli asset, la struttura
> delle sezioni e le note tecniche della pagina `index.html`.
> Aggiornato al: 2026-07-02 · Branch: `claude/dazzling-ride-s6edyl`

---

## 1. IDENTITÀ E DESIGN SYSTEM

### Brand
- **Nome:** Estro Agency (società: YUBA S.r.l.)
- **Posizionamento:** Agenzia di comunicazione per PMI · Milano
- **Logo:** `Logo-estro.webp` (header 42px, footer 34px)
- **Favicon:** `gattino-estro-favicon.png`

### Palette colori (CSS custom properties)
| Variabile | Valore | Uso |
|---|---|---|
| `--K` | `#1C1C1C` | Sfondo principale (nero caldo) |
| `--K2` | `#141414` | Sfondo sezioni alternate |
| `--K3` | `#0E0E0E` | Sfondo scuro profondo |
| `--C` | `#F3EFE0` | Testo principale (crema) |
| `--F` | `#E0185C` | Accento primario (fucsia) |
| `--Y` | `#E8B44A` | Accento secondario (oro) |

### Tipografia
| Ruolo | Font |
|---|---|
| Display / titoli | Special Gothic Expanded One |
| Body | DM Sans |
| Mono / dati | JetBrains Mono |
| Accento corsivo | Caveat |

### Layout
- Container max: `1320px`, padding orizzontale `48px` (desktop) / `20px` / `16px` (mobile)
- Breakpoint principali: 1100px, 900px, 768px, 640px, 480px

---

## 2. STRUTTURA DELLA PAGINA (ordine sezioni)

1. Header fisso + progress bar
2. **Hero** (testo + form, immagine di sfondo full-bleed)
3. **Strip servizi** (banda fucsia statica, una riga)
4. **Marquee loghi clienti** (2 righe animate, direzioni opposte)
5. **Target + Soluzione** (video YouTube + flip card problema/soluzione)
6. **Vantaggi** (3 card numerate)
7. **CTA intermedia**
8. **Servizi** (10 card espandibili)
9. **Metodo** (timeline 4 step)
10. **Benefici** (lista + grafica animata)
11. **Trust** (4 dati numerici grandi)
12. **Social proof** (3 testimonianze)
13. **Form finale contatti**
14. Footer

---

## 3. CONTENUTI SEZIONE PER SEZIONE

### 3.1 HEADER
- Logo Estro (link a #top)
- Nav: Soluzione (#target) · Servizi (#servizi) · Metodo (#metodo) · Chi si fida di noi (#clienti) · Contatti (#contatti)
- CTA: **"Richiedi consulenza ›"** → #contatti
- Mobile: hamburger + overlay con CTA "Consulenza gratuita ›"

### 3.2 HERO
**Sfondo:** `Hero section1.webp` full-bleed con overlay scuro (82%→68% sx→dx).
*(placeholder: verrà sostituito da video quando disponibile — stesso contenitore `.hero-bg`)*

**Colonna sinistra (testo, centrato verticalmente):**
- Badge: `● Agenzia di comunicazione per PMI · Milano`
- H1 (2 righe): **"Un team completo"** / **"a costi sostenibili."** (seconda riga fucsia)
- Sottotitolo: *"Un unico partner per strategia, digital, contenuti e ADV senza il costo di un team interno."*

**Colonna destra (form lead):**
- Titolo form: "Parliamo del tuo progetto"
- Sub: "Nessun impegno · Una conversazione vera"
- Campi: Nome e cognome*, Email*, Numero di telefono*, Azienda*, Sito web (facoltativo), Messaggio
- Submit: **"Invia la richiesta ›"**
- Messaggio successo: "✓ Ricevuto. Vi contatteremo presto."
- Note: "* Campi obbligatori · Privacy Policy"

### 3.3 STRIP SERVIZI (banda fucsia statica)
Una sola riga, allineata ai margini della hero:
`Strategia Digitale · Social Media · Campagne ADV · Content Marketing · SEO · Brand Identity · Email Marketing · Analytics`

### 3.4 MARQUEE LOGHI CLIENTI
- 2 righe a scorrimento continuo, direzioni opposte (55s avanti / 48s indietro, pausa su hover)
- Loghi bianchi (filtro `brightness(0) invert(1)`), altezza ~70-96px
- **49 loghi** dalla cartella `Loghi/` (elenco completo in §4)

### 3.5 TARGET + SOLUZIONE (#target)
- Ghost text sfondo: "FARE DA SOLI."
- Tag: "Hai una PMI?"
- H2: **"Probabilmente sei arrivato fin qui *facendo da solo.*"**
- Lead: "La buona notizia? Non devi continuare così. Esiste un modo migliore"

**Video (YouTube facade, ID: `qRKRdFgKyzs`):**
- Badge: "▶ Guarda il video" · Caption: "Scopri come lavoriamo"
- Chip metriche flottanti: **12+** Anni di esperienza · **90%** Clienti che rinnovano

**Flip card (click per girare):**
- FRONTE — Tag "Il Problema": *"Hai costruito tutto con le tue forze. Anche la comunicazione."*
  - ✕ Marketing senza strategia chiara
  - ✕ Contenuti discontinui e improvvisati
  - ✕ Nessun referente fisso sul tuo brand
  - ✕ Risultati difficili da misurare
  - Corsivo: "Non serve fare di più. Serve farlo meglio."
  - CTA: "Scopri la soluzione ›"
- RETRO — Tag "La Soluzione": **"Un unico partner per tutta la tua *comunicazione.*"**
  - • Strategia costruita sui tuoi obiettivi
  - • Gestione continuativa, non a progetto
  - • Un unico referente che conosce il tuo brand
  - • Report chiari su risultati e prossimi step
  - CTA: "Parliamone insieme ›" → #contatti

**Fact strip:** Strategia su misura · Gestione continuativa · Risultati misurabili

### 3.6 VANTAGGI ("Perché sceglierci")
H2: ***"Tre vantaggi* concreti per le *PMI* che scelgono Estro."**

| # | Titolo | Punto di forza | Descrizione |
|---|---|---|---|
| 01 | Semplificazione totale | Partner unico | Un solo referente, un unico flusso di lavoro. Niente coordinamenti complessi tra agenzie diverse, niente dispersione di energie e budget. |
| 02 | Continuità e strategia | Orientamento al risultato | Non lavoriamo a singole attività. Costruiamo un percorso continuo, con obiettivi chiari e monitorati nel tempo. Ogni azione ha una direzione. |
| 03 | Efficienza dei costi | Pricing accessibile | Accedi a un team completo — strategia, ADV, contenuti — con un investimento più sostenibile rispetto a una struttura interna o a gestire più agenzie. |

CTA: "Richiedi una consulenza gratuita ›" → #contatti

### 3.7 CTA INTERMEDIA
- Ghost text: "ESTRO"
- H2: **"Costruiamo insieme il prossimo passo della tua crescita."**
- Sub: "Un incontro conoscitivo, senza impegno. Parliamo del tuo business e capiamo insieme come possiamo supportarti"
- CTA: "Richiedi una consulenza ›" → #contatti

### 3.8 SERVIZI (#servizi) — 10 card espandibili
H2: **"Cosa facciamo *per te.*"**

| Tag | Servizio | Descrizione |
|---|---|---|
| Core | Strategia Marketing | Obiettivi, analisi del mercato e roadmap operativa con KPI condivisi. |
| ADV | Advertising | Google Ads, Meta, LinkedIn. Campagne misurabili, ottimizzate per massimizzare il ROI. |
| Digital | Comunicazione Digitale | Canali digitali gestiti come sistema unico. Presenza coordinata e risultati misurabili. |
| Creative | Content Creation | Social, web, newsletter con un'unica voce coerente per il tuo brand. |
| Brand | Branding | Identità visiva, posizionamento e tono di voce coerenti su ogni canale. |
| SEO | SEO | Visibilità organica costruita nel tempo. On-page, contenuti e link building. |
| Web | Siti Web & Landing Page | Design e sviluppo orientati alla conversione. Veloci, accessibili, ottimizzati SEO. |
| Social | Social Media Management | Piano editoriale, produzione e community management continuativi. |
| Auto | Marketing Automation | Email flow, CRM e automazioni per nutrire i lead senza lavoro manuale. |
| Intelligence | Analytics & Reporting | Dati chiari e interpretati. Sai sempre cosa funziona e dove investire. |

### 3.9 METODO (#metodo) — timeline 4 step
H2: **"Un metodo semplice e *strutturato.*"** · Tag: "Come lavoriamo"

| Step | Titolo | Sottotitolo | Testo |
|---|---|---|---|
| 01 | Analisi iniziale | e definizione degli obiettivi | Capiamo il tuo business, gli obiettivi e la situazione attuale. Nessuna attività senza una base solida. |
| 02 | Pianificazione strategica | canali, budget e KPI | Piano di marketing, canali, budget e KPI condivisi. Sai esattamente cosa faremo e perché. |
| 03 | Attivazione operativa | campagne, contenuti, strumenti | Lanciamo campagne, contenuti e strumenti. Tutto coordinato, tutto con un obiettivo preciso. |
| 04 | Monitoraggio continuo | e ottimizzazione | Report regolari e ottimizzazione costante. Il piano migliora nel tempo, i risultati crescono. |

Chiusura: **"Sempre con un unico referente e aggiornamenti chiari"** — "Nessuna riunione infinita, nessun rimpallo. Una persona che conosce tutto e ti aggiorna con regolarità."

### 3.10 BENEFICI
H2: **"Cosa ottieni *concretamente.*"** · Tag: "I benefici"
- ✓ Più tempo per concentrarti sul tuo business
- ✓ Maggiore controllo su attività e risultati
- ✓ Comunicazione coerente e continuativa
- ✓ Crescita strutturata, non episodica

CTA: "Parliamone insieme ›" · Grafica: `benefici grafica1.png` con keyword animate: TEMPO · CONTROLLO · COERENZA · CRESCITA

### 3.11 TRUST (#clienti) — dati numerici
Solo 4 numeri grandi (fino a 128px, fucsia), senza box né divisori:

| Valore | Etichetta |
|---|---|
| 10+ | Anni |
| 200+ | Progetti |
| 80+ | Si fidano di noi |
| 90% | Rinnovi |

### 3.12 SOCIAL PROOF — 3 testimonianze (5 stelle ciascuna)
H2: **"Cosa dicono *i nostri clienti.*"** · Lead: "Parole reali, da imprenditori che hanno scelto di smettere di fare tutto da soli"

1. **Marco Rossetti** — CEO · Studio Medico Rossetti · Milano
   > "Da quando lavoriamo con Estro non dobbiamo più preoccuparci di niente. Un unico referente che conosce il nostro business, risponde in tempi rapidi e porta risultati concreti. Il fatturato legato al canale digitale è cresciuto del 60% in un anno."
2. **Laura Conti** — Titolare · Boutique Le Forme · Como
   > "Avevamo provato con freelance diversi e ognuno faceva la sua cosa. Con Estro è completamente diverso: tutto coordinato, tutto coerente. Finalmente il nostro brand comunica in modo professionale e le campagne portano clienti reali."
3. **Andrea Ferretti** — Direttore Commerciale · Elmec Srl · Varese
   > "Il valore di Estro non è solo la competenza tecnica — che c'è eccome — ma l'approccio. Capiscono il tuo business, non ti bombardano di tecnicismi e ti aggiornano con regolarità. Per noi sono diventati una parte essenziale del team."

### 3.13 FORM FINALE (#contatti)
- Tag: "Parliamo del tuo progetto"
- H2: **"Pronti a lavorare su una *regia che funziona.*"**
- Sub: "Niente preventivi al primo contatto. Una conversazione vera su dove volete arrivare e come arrivarci"
- Campi: Nome e cognome*, Email*, Numero di telefono*, Azienda*, Sito web (facoltativo), Messaggio
  - Placeholder messaggio: "Descrivici la situazione attuale: quante persone/agenzie gestite, quali canali usate, cosa non funziona come vorreste."
- Submit: **"Scriveteci ›"**
- Link jobs: "Cerchi invece lavoro o collaborazione? ›" → mailto:jobs@estro.agency

### 3.14 MODAL rapida (da CTA header)
- H3: "Prima di tutto, ascoltiamo." · Sub: "Vi rispondiamo entro 24 ore lavorative."
- Campi: Nome e Cognome*, Email*, Azienda · Submit: "Scriveteci ›"

### 3.15 FOOTER
**YUBA S.r.l.** · C.F./P. IVA 09955650966
- Sede legale: Via Vigevano n. 27, 20144 Milano (MI)
- Sede di Milano: Via Vigevano n.27, 20144 Milano (MI)
- Sede di Varese: Via Mazzini n.1, 21013 Gallarate (VA)
- Social: Instagram · LinkedIn · Facebook · YouTube *(link da fornire, ora `#`)*
- Legal: Privacy Policy · Cookie Policy *(link da fornire)*
- Copyright @2026 Yuba S.r.l.

---

## 4. ASSET

### Immagini nella root
| File | Uso |
|---|---|
| `Logo-estro.webp` | Logo header/footer |
| `Hero section1.webp` | Sfondo hero (placeholder video) |
| `benefici grafica1.png` | Grafica sezione benefici |
| `gattino-estro-favicon.png` | Favicon |
| `Grafica benefici.png`, `grafica header.png`, `elemento-visivo-1.webp` | Asset di riserva/non usati in pagina |

### Cartella `Loghi/` — 49 loghi clienti (webp, tranne redbull.png)
FAMILY, FINESTRATEK, FRAGI, KATE, LOVESUN, MESTEL, NOIKASA, PROXIMA, Prada, abctools, accenture, aprilia, ariston, awlab, biorepair, bocconi, cartier, conde nast, coswell, cupra, disclaimer, elco, elmec, fanuc, gucci, hdllogo, humanitas, kawasaki, l'angelica, lamborghini, leolandia, motoguzzi, pandora, patagonia, plenitude, pyrex, rai, redbull, remax, seat, sector, seven, sj gang, spotify, star, ted, terranova, wolf, wudy

### Video
- YouTube sezione Target: ID `qRKRdFgKyzs` (facade con thumbnail `maxresdefault.jpg`, load on click)
- Video hero: **da fornire** (mp4/webm) — andrà nel contenitore `.hero-bg` al posto dell'immagine

---

## 5. INTERAZIONI / JS PRESENTI
- Header: classe `.on` allo scroll (>40px) + progress bar lettura
- Reveal on scroll (`.rv` → `.vs` con IntersectionObserver)
- Marquee loghi: pausa su hover, rispetta `prefers-reduced-motion`
- Flip card problema/soluzione (click)
- Card servizi espandibili (click) + canvas "nucleus" decorativo
- YouTube facade (carica iframe solo al click)
- Form: submit simulato con messaggio di successo *(backend da collegare)*
- Mobile nav overlay

---

## 6. DA COMPLETARE / FORNIRE
| Item | Stato |
|---|---|
| Video hero (mp4/webm) | ⬜ da fornire — placeholder immagine attivo |
| Backend form (hero, finale, modal) | ⬜ da collegare (ora solo messaggio di successo client-side) |
| Link social footer | ⬜ ora `#` |
| Privacy Policy / Cookie Policy | ⬜ pagine e link da creare |
| Immagini case study (`foto case/`) | ⬜ cartella non presente nella repo |
| Meta description / OG tags / analytics | ⬜ da verificare/aggiungere |
