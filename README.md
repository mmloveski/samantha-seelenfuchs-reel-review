# Seelenfuchs · Hook-Review-Seite

Öffentliche, temporäre GitHub-Pages-Vorschau für die visuelle Hook-Freigabe. Dieses Repository enthält **nur** die statische Webseite und verkleinerte Review-Standbilder, keine Podcastvideos, Transkripte, Schnittdateien, internen Feedback-Notizen oder PDFs. Das lokale Hauptprojekt bleibt außerhalb von Git.

Die Startseite führt Samantha nacheinander durch die noch offenen Hooks. „Fertig – nächste Hook“ blendet den gerade gesichteten Hook auf **diesem Browser/Gerät** aus; die Übersicht oben rechts zeigt ebenfalls nur offene Hooks. Bereits von Samantha freigegebene Hooks werden beim Seitenbau entfernt. Die Webseite sammelt und sendet **kein Feedback**: Samantha spricht es mit der jeweiligen Reel-ID in ihre Handy-AI, die es nach Linear synchronisiert. Ein anderes Gerät übernimmt den lokalen Seitenfortschritt nicht automatisch.

## Aktualisieren

Im übergeordneten Projektordner:

```sh
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
