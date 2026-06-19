# Cite-Konverter für Wikipedia

Der *Cite-Konverter für Wikipedia* unterstützt dich dabei, [`{{cite web}}`](https://de.wikipedia.org/wiki/Vorlage:Cite_web), [`{{cite news}}`](https://de.wikipedia.org/wiki/Vorlage:Cite_news) und [`{{cite magazine}}`](https://en.wikipedia.org/wiki/Template:Cite_magazine) in die deutsche Vorlage [`{{Internetquelle}}`](https://de.wikipedia.org/wiki/Vorlage:Internetquelle) zu konvertieren. Zudem wird [`{{cite book}}`](https://de.wikipedia.org/wiki/Vorlage:Cite_book), [`{{cite journal}}`](https://de.wikipedia.org/wiki/Vorlage:Cite_journal), [`{{cite encyclopedia}}`](https://de.wikipedia.org/wiki/Vorlage:Cite_encyclopedia) und [`{{Citation}}`](https://en.wikipedia.org/wiki/Template:Citation) in [`{{Literatur}}`](https://de.wikipedia.org/wiki/Vorlage:Literatur) konvertiert (bei [`{{Citation}}`](https://en.wikipedia.org/wiki/Template:Citation) ohne Seitenangabe und mit URL alternativ in [`{{Internetquelle}}`](https://de.wikipedia.org/wiki/Vorlage:Internetquelle)).

Das Tool ist eine einzige, eigenständige HTML-Datei – kein Server, keine Installation, keine externen Abhängigkeiten. Einfach herunterladen und im Browser öffnen.

## Intelligente Funktionen

- **Automatische Subreferenzierung:** `{{rp|...}}`-Tags werden automatisch in das `details=`-Attribut konvertiert (z. B. `{{rp|10–20}}` → `details="S. 10–20"`). Mehrere `{{rp}}`-Tags werden zusammengeführt.
- **Wikidata-Integration:** Englische Wikilinks werden automatisch ins Deutsche übersetzt (z. B. `[[Yellowstone National Park]]` → `[[Yellowstone-Nationalpark]]`). Display-Namen bleiben optional erhalten, fehlende deutsche Artikel werden intelligent behandelt. Die Titel werden dabei gebündelt abgefragt, sodass auch viele Wikilinks zügig übersetzt werden.
- **Wikipedia-Redirects:** Automatische Verfolgung von Redirects – englische Wikilinks werden zum finalen Artikel aufgelöst und korrekt ins Deutsche übersetzt (z. B. `[[Eastern Band Cherokee]]` → `[[Eastern Band of Cherokee Indians]]`).
- **Syntax-Highlighting:** Farbliche Hervorhebung für bessere Lesbarkeit von Eingabe und Ausgabe – inklusive grün markierter Wikilinks sowie kursiver (`''…''`) und fetter (`'''…'''`) Wikitext-Formatierung. Abgestimmt für Hell- und Dunkelmodus.
- **Optionale DeepL-Übersetzung** der konvertierten Ausgabe – siehe [eigener Abschnitt](#übersetzung-mit-deepl-optional).

## Übersetzung mit DeepL (optional)

Ab Version 9.0 kann die konvertierte Ausgabe optional per [DeepL](https://www.deepl.com/) ins Deutsche (oder eine andere Zielsprache) übersetzt werden – praktisch, um einen englischen Artikelabschnitt samt Einzelnachweisen zu übertragen.

**Einrichtung**

1. In den Optionen (⚙️) einen DeepL-API-Key eintragen (kostenloser Key mit `:fx`-Endung oder Pro-Key). Der Schlüssel wird ausschließlich lokal im Browser (`localStorage`) gespeichert, bleibt nach dem Schließen erhalten und wird **nur direkt an DeepL** gesendet.
2. Optional die Zielsprache wählen (Standard: Deutsch).
3. Auf „🌐 Übersetzen (DeepL)" klicken – das Ergebnis ersetzt die Ausgabe.

**Was unangetastet bleibt:** Übersetzt wird nur der Fließtext. `<ref>…</ref>` (inklusive selbstschließender `<ref … />`), Wikilinks `[[…]]` sowie Wiki-Kursiv/Fett (`''…''`, `'''…'''`) bleiben unverändert. So bleiben Belege, Verlinkungen und kursive Werktitel exakt erhalten – auch ein entlinkter Werktitel ohne deutschen Artikel bleibt korrekt kursiv (z. B. `''A Blank on the Map''`).

**Wichtiger Hinweis (CORS):** Die DeepL-API erlaubt keine direkten Aufrufe aus dem Browser. Wenn du den Konverter als lokale HTML-Datei nutzt, brauchst du daher eine CORS-Erweiterung (z. B. „CORS Unblock" für Firefox/Chrome). Diese sollte **nur während der Übersetzung** aktiv sein und danach wieder deaktiviert werden, da sie eine Sicherheitsfunktion des Browsers vorübergehend abschaltet. Der Schlüssel verlässt deinen Browser dabei ausschließlich in Richtung DeepL – er läuft über keinen Drittanbieter.

## Wie wird der Konverter genutzt?

Lade die `.html`-Datei herunter und öffne sie im Webbrowser deiner Wahl. Füge im ersten Eingabefeld den zu konvertierenden Code ein, das geht auch inkl. `ref` oder `ref name`. Nach der Nutzung des Buttons „🔀 Konvertieren" findest du im folgenden Feld den nach der Vorlage [`{{Internetquelle}}`](https://de.wikipedia.org/wiki/Vorlage:Internetquelle) bzw. [`{{Literatur}}`](https://de.wikipedia.org/wiki/Vorlage:Literatur) formatierten Einzelnachweis. Die Progress Bar zeigt den Fortschritt bei der Verarbeitung mehrerer Wikilinks und der Auflösung von Redirects. Den kannst du dann einfach kopieren und auf der jeweiligen Wikipedia-Seite einfügen. Bitte prüfe diesen noch einmal manuell vor dem Speichern.

Optionen, Farbschema und Versionsverlauf erreichst du über die Symbole oben rechts: ⚙️ Optionen, 🎨 Farbschema und 📜 Versionsverlauf (jeweils als Fenster/Modal; Schließen per ✕, Klick außerhalb oder `Esc`).

### Optionen

- **Abrufdatum automatisch auf heute setzen** (Wenn aktiviert: Setzt das Abrufdatum des Einzelnachweises immer auf den heutigen Tag, egal was in der Vorgabe steht.)
- **Archiv-Parameter entfernen, wenn URL aktiv** (`url-status=live`) (Alle Archivparameter werden entfernt, wenn die ursprüngliche URL noch vorhanden/live ist.)
- **`Sprache=de` unterdrücken** (Wird bei der Ausgabe nicht ausgegeben, wenn aktiviert.)
- **Ungekürzte Sprachcodes ausgeben** (z. B. `en-GB`) (standardmäßig werden die Sprachcodes auf zwei Stellen gekürzt, `en`, `fr`, usw., auf Wunsch kann das deaktiviert werden.)
- **Sprache manuell überschreiben** (`Sprache=` manuell festlegen anhand der Top-Wikipedia-Sprachen)
- **Subreferenzierung konvertieren** (`{{rp|...}}` → `details=`)
- **Konvertierte Ausgabe direkt in Zwischenablage kopieren**
- **Wikilinks → Deutsch (Wikidata)** (Optional: Automatische Übersetzung englischer Wikilinks via Wikidata-API)
- **Display-Namen beibehalten** (Standardmäßig aktiv: Behält originale Display-Namen bei übersetzten Wikilinks bei)
- **Klammern entfernen bei fehlendem deutschen Artikel** (Standardmäßig aktiv: Entfernt eckige Klammern, wenn kein deutscher Wikipedia-Artikel existiert)
- **DeepL-API-Key & Zielsprache** (Optional, für die DeepL-Übersetzung – siehe oben)
- **Wahl aus rund 37 Farbthemen**
- **Darkmode** (Automatisch, erzwingen oder abschalten)

### Performance

Der Konverter nutzt intelligentes Caching (365 Tage für Wikidata-Übersetzungen, separater Cache für Redirects), gebündelte API-Abfragen und Rate Limiting für optimale Performance und schonenden Umgang mit Wikipedia-/Wikidata-Ressourcen.

## Versionsverlauf

Den vollständigen Verlauf findest du in der [CHANGELOG.md](CHANGELOG.md) sowie direkt im Tool über das 📜-Symbol. Aktuelle Version: **v9.0.2**.

## Lizenz

Veröffentlicht unter der [Unlicense](LICENSE) (Public Domain).
