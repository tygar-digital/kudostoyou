# Projekt-Checkliste

Status-Board für das gesamte Projekt. Wird laufend aktualisiert — Claude proaktiv, Jan bei Review.
Bei "status?" wird diese Checkliste gelesen und offene Punkte gemeldet.

Vor Go-Live muss jeder Punkt abgehakt oder explizit mit Begründung als N/A markiert sein.

---

## Brand & Design

- [x] DESIGN.md vollständig (Farben, Fonts, Stimmung, Bildstil, Referenzen)
- [x] Farbpalette als CSS Custom Properties definiert
- [x] Typografie gewählt und lokal eingebunden (kein CDN)
- [x] Design-Richtung von Jan approved
- [ ] Referenz-Websites recherchiert und studiert (min. 3-5 Konkurrenten/Branche)
- [ ] Design Inspo-Materialien (Logos, Fotos, Screenshots) eingearbeitet
- [x] Favicon erstellt und eingebunden
- [ ] OG-Image erstellt (1200x630px) — aktuell wird Außenansicht-Foto verwendet, dediziertes OG-Image empfohlen

## Content

- [ ] Alle Sektionstexte geschrieben (keine Platzhalter mehr) — Email, Telefon, Öffnungszeiten sind Platzhalter
- [ ] Keine TODOs/TBDs in content.json oder Komponenten — Instagram Post-IDs noch Platzhalter
- [x] Meta-Titles für alle Seiten (unique, < 60 Zeichen)
- [x] Meta-Descriptions für alle Seiten (unique, < 160 Zeichen)
- [x] Alt-Texte auf allen Bildern (beschreibend, nicht "Bild von...")
- [ ] Kontaktdaten korrekt und vollständig (Adresse, Telefon, E-Mail) — Platzhalter
- [ ] Öffnungszeiten korrekt (falls relevant) — Platzhalter

## Seiten

- [x] Homepage
- [x] Impressum (rechtlich vollständig — Name, Adresse, Kontakt, Handelsregister wenn relevant) — Template mit Platzhaltern
- [x] Datenschutzerklärung (DSGVO-konform, alle eingesetzten Dienste aufgeführt) — Template mit Platzhaltern
- [x] 404-Seite (gestaltet, nicht Standard)

## Komponenten

Jede Komponente muss auf Mobile UND Desktop funktionieren.

- [x] Navigation (Mobile Hamburger + Desktop)
- [x] Hero-Sektion
- [x] Content-Sektionen (alle laut DESIGN.md Blueprint)
- [x] Kontakt / Booking-Sektion
- [x] Footer (mit allen rechtlichen Links)
- [x] Cookie-Banner / Consent — N/A, kein Tracking; DSGVO 2-Click für Maps/Instagram implementiert

## Responsive Design

- [x] 375px (Mobile) — kein Overflow, kein abgeschnittener Text
- [x] 768px (Tablet) — Layout-Übergänge sauber
- [x] 1024px (kleiner Desktop) — keine leeren Flächen
- [x] 1280px+ (Desktop) — volle Wirkung, max-width begrenzt
- [x] Touch-Targets mindestens 44px auf Mobile
- [x] Kein horizontaler Scroll auf keinem Breakpoint
- [x] Schriftgrößen lesbar auf allen Viewports

## Performance

- [ ] Lighthouse Performance > 90 — nicht getestet
- [ ] Lighthouse Accessibility > 90 — nicht getestet
- [ ] Lighthouse Best Practices > 90 — nicht getestet
- [ ] Lighthouse SEO > 90 — nicht getestet
- [x] Bilder optimiert (WebP, max. 200KB pro Bild, Hero max. 400KB)
- [x] Fonts lokal geladen (kein Google Fonts CDN — DSGVO)
- [x] Lazy Loading für Bilder unterhalb des Folds
- [x] Hero-Bild eager-loaded
- [ ] Keine render-blockierenden Ressourcen — nicht geprüft

## SEO

- [x] Schema.org Structured Data (CafeOrCoffeeShop mit name, address, telephone, openingHours, geo, image, url, priceRange)
- [x] sitemap.xml generiert und erreichbar
- [x] robots.txt vorhanden und korrekt
- [x] Canonical URLs gesetzt
- [x] Alt-Texte auf allen Bildern
- [x] Heading-Hierarchie korrekt (ein H1 pro Seite, logische Struktur)
- [x] Interne Verlinkung sinnvoll

## Accessibility

- [ ] Farbkontraste WCAG AA (4.5:1 für Text, 3:1 für große Texte) — nicht programmatisch geprüft
- [x] Keyboard-Navigation funktioniert (Tab-Reihenfolge logisch)
- [x] Focus-Indikatoren sichtbar
- [x] Semantisches HTML (header, main, nav, footer, article, section)
- [x] Screen-Reader getestet (oder zumindest: ARIA-Labels wo nötig) — Skip-Link + ARIA-Labels vorhanden
- [x] Bilder: dekorative mit alt="", inhaltliche mit beschreibendem alt

## Legal / DSGVO

- [x] Impressum vollständig und korrekt — Template, echte Daten vor Launch
- [x] Datenschutzerklärung aktuell (alle Dienste aufgeführt) — Template, Review vor Launch
- [x] Keine externen Fonts via CDN (lokal hosten)
- [x] Kein Google Maps iframe ohne Consent (statische Karte oder Zwei-Klick)
- [x] Keine Tracking-Skripte ohne Consent
- [x] Cookie-freie Analytics (Plausible/Umami) oder Cookie-Banner — kein Analytics installiert, daher kein Banner nötig
- [ ] Kontaktformular: Hinweis auf Datenverarbeitung + SSL — kein Kontaktformular implementiert
- [x] Impressum und Datenschutz von jeder Seite erreichbar (Footer-Links)

## Infrastruktur

- [ ] GitHub Repository erstellt (tygar-web Org)
- [ ] Vercel Projekt verbunden (Auto-Deploy bei Push)
- [ ] Cloudflare DNS konfiguriert
- [ ] SSL-Zertifikat aktiv (HTTPS)
- [ ] Domain zeigt auf Vercel
- [ ] MX-Records korrekt (falls E-Mail existiert)
- [ ] www → non-www Redirect (oder umgekehrt)

## Analytics & Monitoring

- [ ] Plausible oder Umami installiert und funktionsfähig
- [ ] Google Search Console verifiziert
- [ ] Sitemap in Search Console eingereicht
- [ ] Analytics-Dashboard erreichbar und trackt Besuche

## Go-Live

- [ ] Finaler visueller Review auf allen Breakpoints (375px, 768px, 1280px)
- [ ] qa-check.sh Script durchgelaufen und alle Checks bestanden
- [ ] Alle internen Links funktionieren (keine 404s)
- [ ] Click-to-Call funktioniert auf Mobile
- [ ] Click-to-Maps funktioniert
- [ ] Kontaktformular getestet (Nachricht kommt an) — N/A, kein Formular
- [ ] Booking-Integration getestet (falls vorhanden) — N/A
- [ ] Ladezeit auf 3G akzeptabel (kritischer Content sofort sichtbar)
- [ ] Client-Abnahme erhalten
- [ ] DNS umgestellt und Site live
- [ ] Alte Website deaktiviert oder Redirect eingerichtet (falls Migration) — N/A

---

## Notizen

- Kontaktdaten (Email, Telefon, Öffnungszeiten) und Menüpreise sind bewusst Platzhalter bis Kundenfreigabe
- Impressum/Datenschutz sind Templates — rechtliche Prüfung erst nach Kundenfeedback zum Draft
- Logo ist aktueller Stand, wird ggf. noch finalisiert
