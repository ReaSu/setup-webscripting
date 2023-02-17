## Was ist das?

Das ist ein Setup für PHP in Containern. Es ersetzt XAMPP. Debugging mit Xdebug in VSCodium[^1] ist konfiguriert, dafür ist das launch.json.

## Voraussetzung: 
Installation von Docker und Docker-Compose. Anleitung im Internet.

(Podman[^2] kann leider noch nicht mit docker-compose umgehen. Aber bald!)

## Wie geht das?
Speicher alle diese Dateien in einem Ordner, z.B. webscripting/myProject/
Falls du git noch nicht kennst, kannst du ein .zip davon herunterladen.

### Was muss wohin?
- Dateien, die über http (Browser oder Milkman[^3] o.ä.) erreichbar sein sollen, gehören in den Ordner app/public. Derzeit liegt dort ein index.php als Beispiel.
- Dateien, die von außen nicht erreichbar sein sollen, können in app/ liegen.

### Starten der Container
Öffne ein Terminal im Ordner, in dem das alles liegt (z.B. webscripting/myProject).

Beim ersten mal starten wir sie mit 

```docker-compose up --build```

Das dauert reht lang, weil vieles heruntergeladen und konfiguriert wird. 

Ab dem zweiten Mal läuft das auch offline, und es reicht als Befehl:

```docker-compose up```

Das ist dann auch schnell.

### Adresse
Was im Ordner app/public liegt, wird über http://127.0.0.1 erreicht. Z.B. findet man eine Datei webscriping/myProject/app/public/meinService.php unter http://127.0.0.1/meinService.php - entweder im Browser oder von Milkman[^2] aus.

### Debugging
Um Xdebug zu starten: Links *Run and Debug* auswählen. Auf das Pfeilchen neben "Listen for Xdebug" klicken, fertig.

### Live Server
Das habe ich noch nicht ausprobiert, kommt später.

## Codium? Podman? Milkman?
- [^1] [Codium](https://vscodium.com/) ist eine Version von VSCode ohne <del>Spionage</del>Telemetrie von Microsoft.
- [^2] [Podman](https://podman.io/) ist eine Alternative zu Docker.
- [^3] [Milkman](https://milkman.dev/) ist eine Alternative zu Postman.

Diese Programme sind FLOSS - [Free and Open Source Software](https://fsfe.org/freesoftware/freesoftware.de.html). 

