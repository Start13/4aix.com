Perfetto Coky 👌
Ecco il **README.md completo, strutturato e professionale** — pronto da incollare nel tuo repository GitHub “4AIX-WebSites”.
È scritto in Markdown e segue uno stile tecnico chiaro, come la documentazione di un progetto reale.
Include tutto: descrizione, struttura, stato lavori, guida tecnica, checklist e piani futuri.

---

# 🌐 4AIX.com — Siti Web & Template Professionali

**Progetto ufficiale:** [https://4aix.com](https://4aix.com)
**Hosting:** GitHub Pages
**Repository:** `4AIX-WebSites`
**Autore:** 4AIX di C. B. (ex BlueTrendTeam)
**Tecnologie:** HTML • CSS • JavaScript • Font Awesome

---

## 🧩 Descrizione del Progetto

Il progetto **4AIX.com** rappresenta la piattaforma ufficiale per la presentazione e la vendita di **template web pronti**, sviluppati in HTML/CSS/JS puri e progettati per aziende, portfolio, e-commerce, gestionali e progetti di trading.

Il sito ha una **home (index.html)** moderna e dinamica, sincronizzata con un sistema di **dark/light mode** e **lingua IT/EN**, e una **pagina template.html** dedicata alla visualizzazione interattiva dei vari modelli disponibili.

---

## 📂 Struttura dei File

```
4AIX.com/
├── index.html              # Homepage principale (dark/light + lingua sincronizzate)
├── template.html           # Catalogo template (in fase di revisione)
│
├── /assets/
│   ├── /css/
│   │   ├── style.css       # Stili globali
│   │   └── template.css    # Stili specifici per la pagina template
│   ├── /js/
│   │   ├── main.js         # Gestione lingua/tema per index.html
│   │   └── template.js     # Gestione filtri e griglia template
│   ├── /img/
│   │   ├── favicon.svg
│   │   ├── logo.svg
│   │   └── /previews/      # Anteprime delle card template
│   └── /lang/
│       ├── it.json         # Traduzioni in italiano
│       └── en.json         # Traduzioni in inglese
│
├── /Template Siti/
│   ├── home/
│   │   └── template.html   # Template base della sezione “home”
│   └── /templates/
│       ├── aziendale/index.html
│       ├── ecommerce/index.html
│       ├── gestionale/index.html
│       ├── portfolio/index.html
│       └── trading/index.html
│
└── README.md               # Documentazione progetto
```

---

## ⚙️ Hosting e Dominio

* **Hosting:** GitHub Pages
* **Dominio collegato:** [https://4aix.com](https://4aix.com)
* Il file `index.html` è servito automaticamente come homepage (nessun `index.html` visibile nell’URL)
* Tutti i link interni usano percorsi relativi o radice (`href="/"`)

---

## 🧠 Funzionalità Implementate

✅ **Tema dark/light sincronizzato**

* Salvato su `localStorage`
* Caricato automaticamente su ogni pagina

✅ **Gestione lingua IT/EN**

* Cambio lingua tramite icona o pulsante dedicato
* Traduzioni gestite via file JSON (`/assets/lang/it.json`, `/assets/lang/en.json`)
* Salvataggio lingua su `localStorage`

✅ **Correzione immagine EasyCardPro**

* Risolto problema di deformazione su mobile
* Applicato `object-fit: cover`, `height: auto` e media query dedicate

✅ **Redirect URL pulito**

* Aggiunto script per rimuovere `index.html` dall’URL:

```html
<script>
  if (window.location.pathname.endsWith("index.html")) {
    window.location.replace(window.location.origin + "/");
  }
</script>
```

Posizionato **prima del tag `</body>`** di `index.html`.

---

## 🧩 Problemi Risolti

| Problema                            | Soluzione                                             | Stato     |
| ----------------------------------- | ----------------------------------------------------- | --------- |
| Immagine deformata in “EasyCardPro” | Aggiunto `object-fit: cover` + media query responsive | ✅ Risolto |
| URL con `/index.html` visibile      | Script JS di redirect automatico                      | ✅ Risolto |
| Icone lingua e tema non coerenti    | Uniformate tra index e template                       | ✅ Risolto |
| Persistenza tema/lingua tra refresh | Sincronizzata tramite `localStorage`                  | ✅ OK      |
| Differenze visive tra dark/light    | Allineate classi e CSS                                | ✅ OK      |

---

## 🔧 Attività in corso

### 1️⃣ Sincronizzazione Lingua tra Pagine

Attualmente, la lingua è salvata in `localStorage` ma non sincronizzata perfettamente:

* Se cambio lingua su `template.html`, `index.html` non aggiorna automaticamente la stessa preferenza.
* Entrambe le pagine devono usare lo stesso script per leggere e impostare la lingua al caricamento.

**Prossimo passo:**
Unificare i selettori e garantire coerenza tra i due file tramite:

```js
const lang = localStorage.getItem("language") || "it";
document.documentElement.lang = lang;
updateLanguageTexts(lang);
```

---

### 2️⃣ Revisione Pagina `template.html`

Dopo la sincronizzazione lingua:

* Migliorare layout con **griglia responsive di card**
* Implementare **filtri per categoria**
* Aggiungere **hover moderni** e ombre leggere
* Rendere tutto coerente con `index.html`
* Preparare struttura futura per **caricamento dinamico da JSON**

---

## 🧭 Linee Guida di Design

* Interfaccia **dark mode di base**
* Layout **pulito, piatto, senza bordi evidenti**
* Tipografia moderna e leggibile
* Stile coerente con `index.html`
* Nessun framework esterno (solo HTML, CSS, JS puri)
* Responsive completo (mobile, tablet, desktop)

---

## ✅ TO-DO OPERATIVO

### 🧭 Fase 1 – Sincronizzazione Lingua

* [ ] Unificare script selettore lingua IT/EN tra `index.html` e `template.html`
* [ ] Assicurarsi che `localStorage.setItem("language")` e `getItem()` funzionino su entrambe
* [ ] Leggere la lingua salvata al `DOMContentLoaded`
* [ ] Aggiornare pulsante e traduzioni (`updateLanguageTexts()`)

### 🎨 Fase 2 – Revisione Grafica Template

* [ ] Creare menu filtrabile per categorie (Aziendale, E-commerce, Portfolio…)
* [ ] Card cliccabili con anteprima, titolo e descrizione
* [ ] Effetti hover moderni e coerenti
* [ ] Ottimizzazione responsive completa

### ⚙️ Fase 3 – UX/UI

* [ ] Transizioni fluide per cambio tema/lingua
* [ ] Migliorare padding e spaziature su mobile
* [ ] Tooltip sulle icone lingua/tema
* [ ] Controllo consistenza dark/light mode

### 📈 Fase 4 – SEO & Pulizia

* [ ] Tutti i link `href="/"`, mai `index.html`
* [ ] Aggiornare `<meta>` SEO e OpenGraph
* [ ] Validare HTML/CSS su [validator.w3.org](https://validator.w3.org)
* [ ] Test redirect automatico da `/index.html` a `/`

### 🔮 Fase 5 – Futuro

* [ ] Creare `templates.json` per caricamento dinamico card
* [ ] Gestione `fetch()` con anteprime aggiornate
* [ ] Implementare ricerca interna per nome o categoria
* [ ] Integrazione con GitHub API per aggiornamento automatico

---

## 🧾 Note Tecniche Finali

* **GitHub Pages** serve automaticamente `index.html` senza mostrarlo nell’URL → nessuna configurazione aggiuntiva richiesta.
* Tutti i collegamenti alla home devono usare `href="/"` o `href="./"`.
* Lo script di redirect JS è sufficiente a pulire l’URL in modo istantaneo.
* Tutto il codice è compatibile con hosting statici.

---

## 📅 Stato attuale

| Area                       | Stato                    | Ultimo aggiornamento |
| -------------------------- | ------------------------ | -------------------- |
| Home (`index.html`)        | ✅ Completa e ottimizzata | 29 Ottobre 2025      |
| Template (`template.html`) | 🟠 In revisione          | 29 Ottobre 2025      |
| Tema/Lingua Sync           | ⚠️ Parziale              | 29 Ottobre 2025      |
| SEO e Redirect             | ✅ OK                     | 29 Ottobre 2025      |

---

## 🧩 Prossimo Step

> Completare la sincronizzazione della lingua tra le pagine, poi passare alla revisione della pagina `template.html` (filtri + card responsive + hover).

---

