# Design System — kudos to you

Café in Bonn · Coffee & Cycling Culture
Minimalistisch, ruhig, handgemacht, menschliche Wärme.

---

## Farbpalette (6 Farben)

| Variable | Hex | Verwendung |
|----------|-----|------------|
| `brand-cream` | `#F5EBDA` | Hintergrund, Sektionen |
| `brand-surface` | `#FFFFFF` | Karten, Container |
| `brand-espresso` | `#2A1810` | Footer, dunkle Akzente |
| `brand-sage` | `#6B4226` | Primary Accent (Buttons, CTAs, Links) |
| `brand-text` | `#3A2E22` | Fließtext, Headlines |
| `brand-muted` | `#9C8470` | Sekundärtext, Divider, Platzhalter |

Opacity-Varianten: `brand-sage/[0.06]` für Hintergründe, `brand-muted/30` für Borders.

## Typografie

| Rolle | Font | Gewicht | Beispiel |
|-------|------|---------|----------|
| Heading | Rubik | 300–900 (meist bold) | Sektions-Headlines, Hero |
| Body | DM Sans | 100–1000 | Fließtext, UI-Elemente |
| Accent | Caveat | 400–700 | Handschrift-Akzente, Labels |

Alle Fonts lokal gehostet (WOFF2), DSGVO-konform. Kein Google Fonts CDN.

### Größen-Hierarchie

- **Hero H1:** `text-[3.2rem]` → `sm:text-6xl` → `md:text-7xl` → `lg:text-[5.5rem]`
- **Sektions H2:** `text-4xl` → `sm:text-5xl` → `lg:text-6xl`
- **Card H3:** `text-lg font-semibold`
- **Body:** `text-base` → `sm:text-lg`
- **Accent:** `font-accent text-base text-brand-sage`

## Spacing

| Token | Wert | Verwendung |
|-------|------|------------|
| `--spacing-section` | `8rem` | Sektions-Padding (Desktop) |
| `--spacing-section-sm` | `5rem` | Sektions-Padding (Mobile) |
| Container | `max-w-7xl` (80rem) | Hauptcontainer |
| Subpages | `max-w-3xl` | Impressum, Datenschutz, 404 |
| Horizontal | `px-6` | Durchgehend auf allen Breakpoints |

## Komponenten

### Buttons
- **Primary:** `rounded-full h-13 bg-brand-sage px-8 text-white` + Hover: `brightness-90 shadow-lg shadow-brand-sage/20`
- **Secondary:** `rounded-full h-13 border-2 border-brand-text px-8` + Hover: `bg-brand-text text-white`

### Karten
`rounded-2xl border border-brand-muted/30 bg-brand-surface p-7` + Hover: `border-brand-sage/40 shadow-lg shadow-brand-sage/5`

### Divider (handgezeichnet)
SVG-Pfad mit `stroke="#3C2415" opacity="0.2"` — organische Kurve, kein gerader Strich.

### Texturen
Zwei Overlay-Layer auf Sektionen:
- `.paper-texture` — SVG Fractal Noise, `opacity: 0.015`
- `.grain` — SVG Fractal Noise, `opacity: 0.04`

## Animation & Motion

### Scroll Reveal
- Easing: `cubic-bezier(0.16, 1, 0.3, 1)`
- Dauer: `0.7s`
- Translate: `24px` nach oben
- Stagger: `80ms` pro Kind-Element
- Trigger: Intersection Observer bei 10%

### Hero
- Cupman: Fade-in (`1.4s`, gleicher Easing, `0.2s` Delay)
- Text-Elemente: `slide-up-fade` gestaffelt (0.2s–1.4s)
- Mouse-Tracking Parallax auf Desktop (lg+)

### Hover
- Image Zoom: `scale(1.03)`
- Sketch Wobble: `0.4s` Rotation
- Transitions: `duration-300` bis `duration-700`

### Reduced Motion
Alle Animationen respektieren `prefers-reduced-motion: reduce`.

## Sektionsstruktur

| Sektion | Ausrichtung | Besonderheit |
|---------|-------------|--------------|
| Hero | Links (Text) + Rechts (Cupman) | Fullscreen, Parallax |
| MarqueeTicker | Horizontal scroll | `●` Separatoren, `cream/60` |
| About | Zweispaltig | Bild füllt volle Spalte |
| Menu | Zentriert | Kategorien mit Preisen |
| Events | Zentriert | Clean Card Layout |
| PhotoScroll | Horizontal scroll | Horizontale Foto-Galerie |
| Gallery/Instagram | Zentriert | DSGVO 2-Click für Embeds |
| Contact | Zweispaltig | Karte + Infos, 2-Click Maps |
| Footer | Espresso-BG | Links, Social, Legal |

## Seitentemplates

### Subpages (Impressum, Datenschutz, 404)
- Container: `max-w-3xl`, `pt-32`, `pb-(--spacing-section)`
- Keine Floating-Dekos, keine Hero-Sektion
- Handgezeichneter SVG-Divider nach Titel
- `space-y-10` für Content-Blöcke
- Zurück-Link am Ende

## Bildstil

- Warm, natürlich, nicht übersättigt
- WebP, max 200KB (Hero max 400KB)
- Lazy Loading unter dem Fold, Hero eager
- Dekorative SVG-Sketches: maximal 1 pro Sektion, sehr dezent (`opacity-10` bis `opacity-[0.12]`)
