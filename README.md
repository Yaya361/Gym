# Freiraum Gym – Landingpage

Eine einseitige Landingpage für die Eröffnung von **Freiraum Gym** im Münsterland. Ziel der Seite ist die Vormerkung von Gründungsmitgliedern über ein Anmeldeformular.

## Überblick

Die Seite ist im reduzierten, Apple-inspirierten Design gehalten (viel Weißraum, dezentes Blau als Akzentfarbe, sanfte Schatten und Bewegungen) und besteht aus einer einzigen `index.html` mit eingebettetem CSS und JavaScript – keine externen Abhängigkeiten außer der Google-Font „Inter".

## Aufbau der Seite

1. **Navigation** – Sticky Header mit Logo und CTA-Button ("Jetzt vormerken")
2. **Hero** – Headline, Subtext und zwei Call-to-Actions
3. **Stats-Bar** – Vier Kennzahlen auf einen Blick (24/7, ab 28 €, 0 € Trainer-Pflicht, 1 Monat Kündigungsfrist)
4. **USP-Grid** – Sechs Vorteilskarten (App-Zugang, flexible Zeiten, Ausstattung, kein Jahresvertrag, Sicherheit, Standortnähe)
5. **Vergleichstabelle** – Freiraum Gym vs. traditionelles Studio
6. **Anmeldeformular** – Vormerkung für Gründungsmitglieder mit Erfolgsmeldung
7. **Footer**

## Funktionsweise

- **Formular**: Das Formular nutzt aktuell `onsubmit="handleSubmit(event)"`, das die Standard-Übermittlung verhindert und stattdessen eine Erfolgsmeldung anzeigt. **Es ist noch keine echte Datenübertragung angebunden** – die eingegebenen Daten gehen aktuell nirgendwo hin. Vor dem Live-Gang muss hier ein Backend, ein Formular-Service (z. B. Formspree, Netlify Forms) oder eine eigene API angebunden werden.
- **Scroll-Animationen**: Ein `IntersectionObserver` beobachtet Elemente mit den Klassen `.reveal` und `.reveal-stagger` und blendet sie sanft ein, sobald sie in den sichtbaren Bereich scrollen (Stats, USP-Karten, Vergleichstabelle, Formular).
- **Responsives Verhalten**: Ab 900 px wechselt das USP-Grid auf 2 Spalten, ab 640 px auf 1 Spalte; die Stats-Bar wechselt unter 640 px auf ein 2×2-Raster; das Formular stapelt sich unter 820 px einspaltig.

## Design-Variablen

Alle Farben, Radien und Abstände sind als CSS-Variablen im `:root`-Block definiert – Anpassungen (z. B. eine andere Akzentfarbe) lassen sich zentral an einer Stelle vornehmen:

```css
--bg, --bg2        Hintergrundfarben
--text, --text2, --text3   Textfarben (Haupttext, sekundär, tertiär)
--accent, --accent-h       Akzentfarbe (Blau) und Hover-Variante
--border                   Rahmenfarbe
--radius-lg/md/sm          Eckenradien
```

## Bekannte offene Punkte / nächste Schritte

- [ ] Formular an einen echten Versand- oder Speicher-Mechanismus anbinden (E-Mail-Benachrichtigung, Datenbank oder CRM)
- [ ] Datenschutzerklärung / Impressum ergänzen (rechtlich notwendig für ein Live-Formular mit Datenerfassung)
- [ ] Eröffnungsdatum und Adresse final eintragen, sobald bekannt
- [ ] Eventuell echte Fotos/Bilder vom Studio ergänzen, sobald verfügbar
- [ ] Cross-Browser- und Mobil-Test vor Launch

## Lokal ansehen

Die Datei kann direkt im Browser geöffnet werden – kein Server oder Build-Schritt notwendig:

```bash
open index.html      # macOS
start index.html     # Windows
```

## Dateien

| Datei | Beschreibung |
|---|---|
| `index.html` | Komplette Landingpage (HTML, CSS, JS in einer Datei) |
| `README.md` | Diese Dokumentation |