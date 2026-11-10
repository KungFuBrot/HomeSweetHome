# HomeSweetHome – Hauskauf-Planer

> Hobbyprojekt. **Online nutzen:** https://kungfubrot.github.io/HomeSweetHome/

Ein Rechner für den Hauskauf: Wie teuer darf das Haus sein, was kosten Nebenkosten und Finanzierung, wann ist es abbezahlt?
Drei Szenarien (niedriges, mittleres, hohes Risiko) werden nebeneinander gerechnet, jeder Schritt ist erklärt.

Die ganze Anwendung ist eine einzige statische HTML-Datei ohne Build-Schritt und ohne Abhängigkeiten.

## Datenschutz und Sicherheit

- **Eingaben verlassen den Browser nicht.** Gespeichert wird nur im `localStorage` des eigenen Browsers. Sicherungen lassen sich als JSON-Datei exportieren und wieder einlesen.
- **Keine Verbindungen nach außen.** Eine Content-Security-Policy verbietet dem Skript jede Netzwerkverbindung (`connect-src 'none'`), Formular-Absendungen und das Nachladen fremder Ressourcen. Schriften (Barlow, SIL OFL 1.1) liegen lokal unter `fonts/`, statt von Google Fonts geladen zu werden.
- **Kein HTML aus Nutzereingaben.** Alle Texte aus Eingaben und importierten Sicherungen werden escaped. Importierte Dateien laufen durch eine Whitelist (`sanitize`), die nur bekannte Felder mit begrenzten Wertebereichen übernimmt.
- **Teilen per Link überträgt keine Daten.** Der `#Anker` in der Adresszeile klappt nur einen Abschnitt auf und wird vorher geprüft.

## Lokal starten

`index.html` direkt im Browser öffnen, oder mit einem beliebigen statischen Server, z. B.:

```bash
npx http-server . -p 8765
```
