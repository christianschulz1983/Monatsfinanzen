# Monatsfinanzen

Web-App für die monatliche Haushaltsplanung: Einnahmen, Fixkosten, variable Ausgaben,
Tagesbudget und Auswertung – als **eine einzige HTML-Datei**, die im Browser läuft.
Kein Server, kein Konto, keine Installation.

## Funktionen

**Übersicht**
- Monatliches Einkommen und Fixkosten selbst anlegen, Summe wird laufend gerechnet
- Ausgabebuch mit neun Kategorien (Lebensmittel, Tanken/Auto, Kinder, Freizeit …)
- Verbleibender Puffer als große Kennzahl, farbig nach Lage (grün / gelb / rot)
- Optionales Tagesbudget mit Hochrechnung auf den Monat
- Belegscan: Foto oder PDF auswählen, Betrag wird per Texterkennung vorgeschlagen;
  der Beleg hängt anschließend an der Ausgabe und lässt sich vergrößern
- Monatsnavigation: ein neuer Monat übernimmt Einkommen und Fixkosten des Vormonats,
  die variablen Ausgaben starten leer

**Auswertung**
- Verfügbarer Betrag und Verbrauch im Monatsverlauf
- Kategorienverteilung als Ringdiagramm
- Durchschnitt pro Tag und pro Monat
- Vergleich zum zuletzt erfassten Monat
- Jahresauswertung mit Monatsbalken und Kategorien des Jahres
- Bericht als PDF exportieren

## Starten

Die Datei `index.html` genügt – Doppelklick, fertig. Alternativ über GitHub Pages
im Browser aufrufen (Settings → Pages → Branch `main`, Ordner `/`).

Für Belegscan und PDF-Export lädt die Seite vier Bibliotheken von öffentlichen CDNs
(jsPDF, jsPDF-AutoTable, tesseract.js, pdf.js). Ohne Internet funktioniert alles
Übrige weiterhin, nur diese beiden Zusatzfunktionen nicht.

## Datenschutz

Alle Zahlen und Belege liegen ausschließlich im `localStorage` des jeweiligen Browsers.
Es werden keine Daten übertragen, gespeichert oder ausgewertet – auch nicht bei
Nutzung über GitHub Pages.

Im Quelltext stehen **keine** Finanzdaten: Die App startet mit einem Einkommen von 0 €
und ohne Fixposten. Einkommen, Fixkosten und Ausgaben trägt jeder selbst ein; sie
bleiben im Browser und gelangen nie in dieses Repository.

Weil die Daten im Browser liegen, gilt: anderer Browser oder anderes Gerät bedeutet
ein leerer Stand, und gelöschte Browserdaten löschen auch die Erfassung.
Der PDF-Bericht eignet sich zur Sicherung außerhalb des Browsers.
