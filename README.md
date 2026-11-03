# Seelenfuchs · Hook-Review-Seite

Öffentliche, temporäre GitHub-Pages-Vorschau für die visuelle Hook-Freigabe. Dieses Repository enthält **nur** die statische Webseite, verkleinerte Review-Standbilder und die gesprochenen Reel-Ausschnitte als Transkript, keine Podcastvideos, vollständigen Folgentranskripte, Schnittdateien, internen Feedback-Notizen oder PDFs. Das lokale Hauptprojekt bleibt außerhalb von Git.

Die Startseite führt Samantha nacheinander durch die noch offenen Hooks. In der kompakten Kopfzeile steht „Folge 6 · Reel 1“; Samantha sagt ihrer Handy-AI jeweils zuerst „Folge 6, Reel 1“ und dann ihr Feedback. Diese Kombination ist projektweit eindeutig und entspricht der internen ID `F06-R01` (allgemein: `Folge N, Reel M` → `FNN-RMM`, beide Zahlen zweistellig). Die interne ID bleibt für Dateien, Bibliothek und Verarbeitung des Linear-Feedbacks erhalten. Die Übersicht zeigt ebenfalls die gesprochene Form.

Neben dem Hook-Bild steht die geschnittene Konversation als Chat: Gast links, Samantha rechts. Die Texte werden aus den finalen Hörproben-Transkripten und den dokumentierten Sprecherabschnitten erzeugt; automatische Worterkennung kann im Detail fehlerhaft sein. „Fertig – nächste Hook“ blendet den gerade gesichteten Hook auf **diesem Browser/Gerät** aus; die Übersicht oben rechts zeigt ebenfalls nur offene Hooks. Bereits von Samantha freigegebene Hooks werden beim Seitenbau entfernt. Die Webseite sammelt und sendet **kein Feedback**: Samantha spricht es mit Folge und Reel in ihre Handy-AI, die es nach Linear synchronisiert. Ein anderes Gerät übernimmt den lokalen Seitenfortschritt nicht automatisch.

## Aktualisieren

Im übergeordneten Projektordner:

```sh
python3 04-Werkzeuge/build_reel_review_conversations.py
python3 04-Werkzeuge/build_hook_review_round2.py  # erzeugt Standbilder/PDFs und prüft die Label-Zentrierung
python3 04-Werkzeuge/build_hook_review_site.py
git -C 09-Hook-Review-Seite add docs
git -C 09-Hook-Review-Seite commit -m "Update hook review"
git -C 09-Hook-Review-Seite push
```

Nach jeder Änderung an Hooks zuerst den Standbild- und PDF-Freigabeprozess im Hauptprojekt durchlaufen. Die Seite spiegelt die jeweils aktuelle Review-Runde; eine Veröffentlichung ist keine Freigabe für vollständige Videoexports.

## Nach Abschluss offline nehmen

GitHub Pages deaktivieren:

```sh
gh api -X DELETE repos/mmloveski/samantha-seelenfuchs-reel-review/pages
```

Das deaktiviert den Website-Link. Weil das Repository öffentlich ist, bleiben die committed Bilder danach **weiter im Repository sichtbar**. Soll auch das wegfallen, das Repository anschließend privat stellen oder löschen. Bereits heruntergeladene Kopien und Suchmaschinen-Caches lassen sich nicht zurückholen. `robots.txt` und `noindex` reduzieren nur die Indexierung; sie sind keine Zugangssperre.
