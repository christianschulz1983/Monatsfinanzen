# Monatsfinanzen

Web-App für die monatliche Haushaltsplanung: Einnahmen, Fixkosten, variable Ausgaben,
Tagesbudget und Auswertung – als **eine einzige HTML-Datei**, die im Browser läuft.
Kein Server, kein Konto, keine Installation.

## Funktionen

**Drei Reiter**
- Heute: was heute und diesen Monat noch zur Verfügung steht, mit offengelegter Herleitung
  und Erfahrungswert aus den letzten sechs Monaten; ein Statussatz aus den eigenen Zahlen,
  der die eigene Datenlage prüft (fehlende Fixkosten, zu wenige Buchungen) statt zu raten;
  Hinweis auf anstehende Zahlungen – und die Erfassung (Schnellzeile, Beleg, Auszug)
- Monat: jede Ausgabe des Monats, Einnahmen und Fixkosten, geplante Einmalausgaben,
  90-Tage-Vorschau, Kassensturz
- Statistik: Kategorien, Durchschnitte, Verlauf, Jahr, Auffälligkeiten, Rücklagen, Backup

**Erfassen**
- Monatliches Einkommen und Fixkosten selbst anlegen, Summe wird laufend gerechnet
- Fälligkeitsdatum und Rhythmus je Fixposten (monatlich bis jährlich); wahlweise auf die
  Monate verteilt, nur im Fälligkeitsmonat gebucht, beides zugleich (Anteil im Puffer,
  Hinweis im Fälligkeitsmonat) oder vorübergehend gar nicht gerechnet
- Fixkosten aus Kontoauszug, Schreiben oder Aufstellung einlesen (PDF oder Foto):
  erkannte Posten erscheinen als Vorschlagsliste, übernommen wird nur das Angehakte;
  ein bereits bekannter Posten bekommt den neuen Betrag statt eines zweiten Eintrags
- Geplante Einmalausgaben (TÜV, Urlaub, Reparatur) mit Datum; mindern das verfügbare Geld
  und erscheinen in der Vorschau
- Schnell-Erfassung: Betrag, Zweck und Kategorie in einer Zeile („12,50 Rewe Lebensmittel"),
  Diktat über die Tastatur möglich; Datum und Kategorie daneben zum Nachbessern, eine
  von Hand gewählte Kategorie wird nicht überschrieben
- „Zuletzt gebucht" mit Löschknopf je Zeile
- Kontoauszug als Ausgaben-Import: Kartenzahlungen und Lastschriften mit Datum, Betrag und
  geratener Kategorie; bereits erfasste Buchungen und Fixposten werden gekennzeichnet
- Händler-Gedächtnis: eine korrigierte Kategorie gilt beim nächsten Mal automatisch
- Ausgabebuch mit neun Kategorien (Lebensmittel, Tanken/Auto, Kinder, Freizeit …)
- Verbleibender Puffer als große Kennzahl, farbig nach Lage (grün / gelb / rot)
- Optionales Tagesbudget mit Hochrechnung auf den Monat
- Belegscan: Foto oder PDF auswählen, Betrag wird per Texterkennung vorgeschlagen;
  der Beleg hängt anschließend an der Ausgabe und lässt sich vergrößern
- Monatsnavigation: ein neuer Monat übernimmt Einkommen und Fixkosten des Vormonats,
  die variablen Ausgaben starten leer

**Vorschau**
- 90-Tage-Vorschau des Kontostands aus Einkommenstag, Fälligkeiten und durchschnittlichem
  Tagesverbrauch; nennt Tag und Betrag des tiefsten Punktes und die nächsten Zahlungen
- gerechnet wird der tatsächliche Zahlungsfluss – auch bei Posten, die im Monatsdurchschnitt
  geführt werden

**Auswertung**
- Verfügbarer Betrag und Verbrauch im Monatsverlauf
- Kategorienverteilung als Ringdiagramm
- Durchschnitt pro Tag und pro Monat
- Vergleich zum zuletzt erfassten Monat
- Jahresauswertung mit Monatsbalken und Kategorien des Jahres
- Auffällig: Kategorien, die um mehr als 15 € und ein Viertel vom eigenen Schnitt der
  letzten sechs Monate abweichen (im laufenden Monat stichtagsgenau verglichen)
- Rücklagen: was für verteilt gerechnete Posten bis heute beiseitegelegt sein müsste
- Kassensturz: ein neu eingetragener Kontostand wird gegen den rechnerischen verglichen;
  die Differenz lässt sich als vergessene Ausgabe nachbuchen
- Fälligkeiten als Kalenderdatei (.ics) mit Wecker sieben Tage vorher
- Einzelposten vom Kassenbon einzeln buchen, mit Kategorievorschlag
- Beträge wahlweise zusätzlich in Arbeitszeit
- Bericht als PDF exportieren

## Starten

Im Browser: https://christianschulz1983.github.io/Monatsfinanzen/

Ohne Internet genügt die Datei `index.html` – Doppelklick, fertig.

Wie man sie bedient, steht in der Kurzanleitung:
https://christianschulz1983.github.io/Monatsfinanzen/anleitung.html
(`anleitung.html`, in der App unten verlinkt).

### Auf dem iPhone als App

In **Safari** die Adresse öffnen, unten auf **Teilen** → **Zum Home-Bildschirm**.
Die App startet danach im Vollbild ohne Adressleiste, mit eigenem Symbol.

Wichtig: iOS führt für eine so installierte App einen **eigenen Speicher**, getrennt
von Safari. Was in Safari eingetragen wurde, erscheint dort nicht – am besten von
Anfang an nur über das Symbol auf dem Home-Bildschirm arbeiten.

`manifest.webmanifest` und die drei `icon-*.png` machen die Seite zur installierbaren
Web-App (Symbol, Vollbild, Startfarbe); für den reinen Browserbetrieb sind sie entbehrlich.

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
