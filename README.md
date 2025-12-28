# Cite-Konverter für Wikipedia
Der <i>Cite-Konverter für Wikipedia</i> unterstützt dich dabei, <a href="https://de.wikipedia.org/wiki/Vorlage:Cite_web" target="_blank"><code>{{cite web}}</code></a>, <a href="https://de.wikipedia.org/wiki/Vorlage:Cite_news" target="_blank"><code>{{cite news}}</code></a> und <a href="https://en.wikipedia.org/wiki/Template:Cite_magazine" target="_blank"><code>{{cite magazine}}</code></a> in die deutsche Vorlage <a href="https://de.wikipedia.org/wiki/Vorlage:Internetquelle" target="_blank"><code>{{Internetquelle}}</code></a> zu konvertieren. Zudem wird <a href="https://de.wikipedia.org/wiki/Vorlage:Cite_book" target="_blank"><code>{{cite book}}</code></a>, <a href="https://de.wikipedia.org/wiki/Vorlage:Cite_journal" target="_blank"><code>{{cite journal}}</code></a> und <a href="https://de.wikipedia.org/wiki/Vorlage:Cite_encyclopedia" target="_blank"><code>{{cite encyclopedia}}</code></a> in <a href="https://de.wikipedia.org/wiki/Vorlage:Literatur" target="_blank"><code>{{Literatur}}</code></a> konvertiert.

## Intelligente Funktionen
* Automatische Subreferenzierung: <code>{{rp|...}}</code>-Tags werden automatisch in das <code>details=</code>-Attribut konvertiert (z. B. <code>{{rp|10–20}}</code> → <code>details="S. 10–20"</code>). Mehrere <code>{{rp}}</code>-Tags werden zusammengeführt.
* Wikidata-Integration: Englische Wikilinks werden automatisch ins Deutsche übersetzt (z. B. <code>[[Yellowstone National Park]]</code> → <code>[[Yellowstone-Nationalpark]]</code>). Display-Namen bleiben optional erhalten, fehlende deutsche Artikel werden intelligent behandelt.
* Wikipedia-Redirects: Automatische Verfolgung von Redirects – englische Wikilinks werden zum finalen Artikel aufgelöst und korrekt ins Deutsche übersetzt (z. B. <code>[[Eastern Band Cherokee]]</code> → <code>[[Eastern Band of Cherokee Indians]]</code>).
- Syntax-Highlighting: Farbliche Hervorhebung für bessere Lesbarkeit von Eingabe und Ausgabe.

## Wie wird der Konverter genutzt?
Lade die .html-Datei herunter und öffne sie im Webbrowser deiner Wahl. Füge im ersten Eingabefeld den zu konvertierenden Code ein, das geht auch inkl. <code>ref</code> oder <code>ref name</code>. Nach der Nutzung des Buttons „🔀 Konvertieren" findest du im folgenden Feld den nach der Vorlage <a href="https://de.wikipedia.org/wiki/Vorlage:Internetquelle" target="_blank"><code>{{Internetquelle}}</code></a> bzw. <a href="https://de.wikipedia.org/wiki/Vorlage:Literatur" target="_blank"><code>{{Literatur}}</code></a> formatierten Einzelnachweis. Die Progress Bar zeigt den Fortschritt bei der Verarbeitung mehrerer Wikilinks und der Auflösung von Redirects. Den kannst du dann einfach kopieren und auf der jeweiligen Wikipedia-Seite einfügen. Bitte prüfe diesen noch einmal manuell vor dem Speichern.

### Optionen
* Abrufdatum automatisch auf heute setzen (Wenn aktiviert: Setzt das Abrufdatum des Einzelnachweises immer auf den heutigen Tag, egal was in der Vorgabe steht.)
* Archiv-Parameter entfernen, wenn URL aktiv (<code>url-status=live</code>) (Alle Archivparameter werden entfernt, wenn die ursprüngliche URL noch vorhanden/live ist.)
* <code>Sprache=de</code> unterdrücken (Wird bei der Ausgabe nicht ausgegeben, wenn aktiviert.)
* Ungekürzte Sprachcodes ausgeben (z. B. <code>en-GB</code>) (standardmäßig werden die Sprachcodes auf zwei Stellen gekürzt, <code>en</code>, <code>fr</code>, usw., auf Wunsch kann das deaktiviert werden.)
* Konvertierte Ausgabe direkt in Zwischenablage kopieren
* Wahl aus acht verschiedenen Designs
* Darkmode (Automatisch, erzwingen oder abschalten)
* Sprache manuell überschreiben (<code>Sprache=</code> manuell festlegen anhand der Top-Wikipedia-Sprachen)
* Wikilinks → Deutsch (Wikidata) (Optional: Automatische Übersetzung englischer Wikilinks via Wikidata-API)
* Display-Namen beibehalten (Standardmäßig aktiv: Behält originale Display-Namen bei übersetzten Wikilinks bei)
* Klammern entfernen bei fehlendem deutschen Artikel (Standardmäßig aktiv: Entfernt eckige Klammern, wenn kein deutscher Wikipedia-Artikel existiert)

### Performance
Der Konverter nutzt intelligentes Caching (365 Tage für Wikidata-Übersetzungen, separater Cache für Redirects) und Rate Limiting (100 ms zwischen API-Calls) für optimale Performance und schonenden Umgang mit Wikipedia-/Wikidata-Ressourcen.
