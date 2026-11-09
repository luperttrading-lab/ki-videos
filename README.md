# KI-Videos

Erklärvideos rund um KI-Werkzeuge, veröffentlicht über GitHub Pages:
[luperttrading-lab.github.io/ki-videos](https://luperttrading-lab.github.io/ki-videos/)

## Aufbau

- `index.html`: Übersicht, je Video eine Karte
- `<video-name>/index.html`: Videoseite mit Player, Kapitelsprüngen und Quellen
- `<video-name>/video.mp4`, `poster.jpg`: Web-Fassung des Videos und Titelbild
- `stil.css`: gemeinsames Aussehen; `.nojekyll`: Seiten werden ohne Jekyll ausgeliefert

## Neues Video hinzufügen

1. Ordner anlegen, Videoseite aus `opencode-browse/index.html` kopieren und anpassen.
2. Web-Fassung erzeugen (Folienvideos: kein sichtbarer Verlust, etwa 1,3 MB pro Minute):

       ffmpeg -i original.mp4 -c:v libx264 -preset slow -tune animation -crf 32 -pix_fmt yuv420p \
         -c:a aac -b:a 64k -ac 1 -movflags +faststart video.mp4

3. Karte in `index.html` ergänzen.

Platz: GitHub Pages erlaubt rund 1 GB je Seite, einzelne Dateien höchstens 100 MB.

## Quellcode der Videos

- OpenCode Browse: `video/opencode-browse/` im Repo `luperttrading-lab/fragen-allgemein`
  (Branch `claude/great-shannon-ogssbk`): Remotion-Projekt, Sprechtext, ElevenLabs-Aufnahmen, Faktencheck.
