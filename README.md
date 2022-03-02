# Fivem Profiler

Der Fivem-Profiler funktioniert. Es ist nur etwas eigen in der Handhabung. Folgend die Erklärung zweier Nutzungsmöglichkeiten:

## Server-Variante
 - Performance-Profil erstellen
```
profiler record 100 (hier als Beispiel 100 Frames)
profiler view (sobald der Profiler mit dem Recording fertig ist)
```

 - **LINK** vorbereiten: http://SERVERIP:SERVERPORT/profileData.json (Bspw.: http://45.81.235.239:30120/profileData.json für den Dev-Server)
 --> zwei Möglichkeiten zum Anzeigen der Daten:
#### Möglichkeit 1:
```
Link nach loadTimelineFromURL mit gerade erstelltem LINK ersetzen: https://chrome.../inspector.html?loadTimelineFromURL=LINK
Bsp.: https://chrome-devtools-frontend.appspot.com/serve_rev/@901bcc219d9204748f9c256ceca0f2cd68061006/inspector.html?loadTimelineFromURL=http://45.81.235.239:30120/profileData.json
```
#### Möglichkeit 2:
```
Aufrufen von LINK und Speichern des Files mit STRG+S
Laden des gespeicherten Files im Chrome Performance-Viewer
```

**Wichtig** ist, dass der "profiler view" - Befehl verwendet wird, damit das JSON-File generiert wird.
Der Profiler kann außerdem **aus einem auf den Server geladenen .bin-File ein Performanceprofil generieren.** Dies über den Befehl "profiler view filename.bin" möglich.
Der Speicherort der .bin-Files ist standardmäßig der "server-data"-Ordner.

## Client-Variante
 - .bin-File kann von Client oder vom Server stammen 
 - Ablegen von .bin-File unter "%localappdata%\FiveM\FiveM.app\citizen\"
 - Öffnen des Fivem-Client im Dev-Mode (Latest Unstable)
 - File kann ähnlich Server-Variante über Befehl "profiler view filename.bin" ausgewertet werden (Im Hauptmenü machbar)
 - Browserfenster mit Performance-Viewer öffnet sich

P.S.:Im Forum wird erwähnt, den Profiler nicht zu exzessiv zu verwenden, da dieser Synchron läuft und sich vehement auf die Performance auswirkt. Eher auf Dev, nicht auf Main und nicht zu Stoßzeiten nutzen.