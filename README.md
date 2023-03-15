## Was ist das?

Das ist ein Setup für PHP in Containern, und ersetzt XAMPP. Anstatt Apache wird nginx verwendet, außerdem ist Debugging mit Xdebug in Codium[^1] bereits konfiguriert (s. .vscode/launch.json).

Derzeit ist weder eine Datenbank noch Perl enthalten, daher ist es kein vollständiger Ersatz für XAMPP - aber es reicht für diese Aufgabe.

## Voraussetzung:
- Docker
    - Installation für [Windows](https://docs.docker.com/desktop/install/windows-install/)
    - Installation für [Mac](https://docs.docker.com/desktop/install/mac-install/)
    - Installation für [Linux](https://docs.docker.com/desktop/install/linux-install/)
- Codium oder VSCode
    - Plugin PHP Debug (xdebug)
    - Plugin Live Server (ritwickdey)
- Browser
    Extension zum Live Server (s. Installation Live Server Plugin)

### empfohlen:
Plugins für Codium:
- PHP Intelephense
- jQuery Code Snippets
- HTML CSS Support
- Auto Close Tag
- Auto Rename Tag
- Bootstrap 5 & FontAwesome

## Wie geht das?
Zip entpacken, weitere Infos unten lesen.
Alles ist schon konfiguriert und sollte out of the box funktionieren.

### Was muss wohin?
- Dateien, die über http (Browser oder Milkman[^2] o.ä.) erreichbar sein sollen, gehören in den Ordner **```app/public```**. Derzeit liegt dort ein index.php als Beispiel, und der Client aus der Beispielanwendung. Auch der ServiceHandler ist public.
- Dateien, die von außen nicht erreichbar sein sollen, liegen im Ordner **```app/```**, aber außerhalb von ```public```.

### Starten der Container
Öffne ein Terminal im Ordner, in dem das alles liegt (z.B. webscripting/myProject) - am besten gleich in VS Codium.

Beim ersten Mal bauen und starten wir die Container mit

```docker-compose up --build```

Das dauert etwas, weil alles heruntergeladen und konfiguriert wird.

Ab dem zweiten Mal reicht als Befehl:

```docker-compose up```

Das funktioniert dann auch offline, und der container ist schnell gestartet.

### Adresse
Was im Ordner **```app/public/```** liegt, wird über http://127.0.0.1 erreicht.

Z.B. findet man eine Datei app/public/meinService.php unter http://127.0.0.1/meinService.php - entweder im Browser oder von Milkman[^2] aus.

### Debugging
Um Xdebug zu starten: Links *Run and Debug* auswählen. Auf das Pfeilchen neben "Listen for Xdebug" klicken.

### Live Server
In der Browser-extension das Hakerl bei "I don't want proxy setup (recommended)" entfernen.

Derzeit funktioniert ENTWEDER Xdebug ODER Live Server. Muss erst mit den Einstellungen spielen, damit beides gleichzeitig geht.

## Codium? Milkman?
- [^1] [Codium](https://vscodium.com/) ist eine Version von VSCode ohne <del>Spionage</del>Telemetrie von Microsoft.
- [^2] [Milkman](https://milkman.dev/) ist eine Alternative zu Postman.

Diese Programme sind FLOSS - [Free and Open Source Software](https://fsfe.org/freesoftware/freesoftware.de.html).
