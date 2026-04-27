# ⚡ Image Vision Studio

> **Real-time image effects engine** — 7 WebGL/Canvas efektov, webcam podpora, drag & drop, svetlý/tmavý režim. Čisto klientská aplikácia bez backendu.

![thumbnail](thumbnail.png)

---

## 🎯 O projekte

**Image Vision Studio** je interaktívna webová aplikácia vytvorená ako súčasť predmetu **B-MSAP** (Multimediálna webová služba). Umožňuje používateľovi nahrať fotografiu alebo zapojiť webkameru a v reálnom čase aplikovať vizuálne efekty implementované pomocou **WebGL GLSL shaderov** a **HTML5 Canvas API**.

Celá logika beží **výhradne v prehliadači** — žiadny backend, žiadny server, žiadne externé API.

---

## ✨ Efekty

| Efekt | Technológia | Popis |
|---|---|---|
| ⚡ **Cyber Glitch** | GLSL Fragment Shader | RGB split, horizontálne posuny, scan-line korupcia |
| 🔮 **Neon Edge** | GLSL · Sobel operátor | Detekcia hrán s pulzujúcou neon farbou na čiernom pozadí |
| 🌡️ **Thermal** | GLSL Fragment Shader | Teplotná mapa (modrá → fialová → červená → žltá) |
| 📟 **ASCII Art** | Canvas 2D | Transformácia obrazu na farebné ASCII znaky v reálnom čase |
| 🌀 **Kaleidoskop** | GLSL Fragment Shader | Zrkadlenie do 4–12 segmentov, rotácia podľa pohybu myši |
| ⏱️ **Time Warp** | Canvas 2D | Horizontálny sken — živý obraz vs. zmrazený čas |
| 🎨 **Oil Paint** | GLSL · Kuwahara Filter | Transformácia na štýl olejomaľby, zachovanie hrán |

---

## 🚀 Ako používať

### 1. Vstup
- **📷 Kamera** — klikni na tlačidlo `KAMERA` alebo `Štart Kamera`, prehliadač požiada o povolenie
- **📁 Upload** — klikni `UPLOAD` alebo potiahni súbor (JPG · PNG · WEBP) priamo do okna

### 2. Efekty
Klikni na tlačidlo efektu v spodnom paneli. Každý efekt sa okamžite aplikuje na živý vstup.

> **⏱ Time Warp** je špeciálny — po prvom kliknutí prepneš na efekt, **druhým kliknutím spustíš sken**. Scanline prejde celým obrazom raz a zastaví sa.

### 3. Intenzita
- Slider **INTENZITA** ovláda silu efektu
- Koliesko myši nad canvasom tiež mení intenzitu
- Pre Oil Paint kontroluje polomer Kuwahara filtra

### 4. Uloženie
Tlačidlo **💾 ULOŽIŤ** stiahne aktuálny frame ako PNG s bielo-záblesk efektom.

### 5. Reset
Tlačidlo **×** v rohu canvasu zastaví kameru, vymaže obrázok a vráti aplikáciu do úvodného stavu.

---

## 🛠️ Technický stack

```
HTML5 + CSS3 + JavaScript (ES2020)
├── WebGL 1.0 (GLSL ES 1.0)
│   ├── Cyber Glitch shader
│   ├── Neon Edge (Sobel) shader
│   ├── Thermal Vision shader
│   ├── Kaleidoscope shader
│   └── Oil Paint (Kuwahara) shader — precision highp float
├── Canvas 2D API
│   ├── ASCII Art renderer
│   ├── Time Warp scan system
│   ├── Vignette + Film Grain overlay
│   └── Webcam mirror buffer
└── Google Fonts — Space Grotesk
```

**Žiadne závislosti.** Žiadny npm, žiadny build step. Jeden súbor `index.html`.

---

## 🎨 UI/UX features

- **Dark / Light Mode** — prepínač ☀️/🌙 v pravom hornom rohu
- **Glassmorphism** design — `backdrop-filter: blur` panely
- **Drag & Drop** — potiahni obrázok priamo do okna
- **Snapshot Flash** — biely záblesk pri uložení
- **Film Grain + Vignette** — subtílny filmový overlay
- **Responzívny** — prispôsobí sa rozlíšeniu zdroja
- **Error handling** — prehľadné hlášky pri zamietnutí kamery

---

## 📁 Štruktúra repozitára

```
├── index.html       ← celá aplikácia (HTML + CSS + JS + GLSL)
├── thumbnail.png    ← náhľad pre portál (1000 × 1000 px)
└── README.md        ← tento súbor
```

---


## 🧩 Zaradenie do portálu B-MSAP

Projekt je navrhnutý pre integráciu do centrálneho portálu:

- `index.html` obsahuje tlačidlo **← Späť na portál** (`href="/"`)
- `thumbnail.png` má rozmer presne **1000 × 1000 px**
- Žiadny backend — aplikácia pobeží aj o roky bez údržby

---

## 👤 Autor

**Dominik Kudela** · B-MSAP · 2025/2026

---

*Image Vision Studio — kde každý pixel rozpráva príbeh.*