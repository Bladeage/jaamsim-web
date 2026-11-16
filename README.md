# JaamSim im Browser (Probe)

Startet die Java-Anwendung [JaamSim](https://jaamsim.com) ohne Installation im Browser, über [CheerpJ](https://cheerpj.com) (Java 17 als WebAssembly).
**Status: Machbarkeitstest.** Die 3D-Modellansicht nutzt JOGL/OpenGL mit nativen Bibliotheken – die laufen im Browser voraussichtlich nicht.

- **Seite:** https://bladeage.github.io/jaamsim-web/ (Oberfläche) · `?mode=headless` (Rechenlauf ohne Grafik mit `beispiel/warteschlange.cfg`)
- **Version wechseln:** in `jaamsim-version.txt` `latest` oder einen Tag wie `v2026-08` eintragen → die Action lädt die `.jar` aus den
  [JaamSim-Releases](https://github.com/jaamsim/jaamsim/releases) und veröffentlicht neu. Die `.jar` liegt nicht im Repo.

## Wie es funktioniert

1. `.github/workflows/pages.yml` holt die JaamSim-`.jar` per `gh release download` (Browser dürfen Release-Dateien wegen CORS nicht direkt laden)
   und schreibt `build-info.json` mit Release und Dateiname.
2. `index.html` lädt CheerpJ 5.0, startet die `.jar` aus dem eigenen Pages-Ordner (`/app/<repo>/…`).

## Lizenzen

JaamSim: Apache 2.0 (`LICENSE-JaamSim.txt`, unverändert weitergegeben). CheerpJ: kostenlos für private/nicht-kommerzielle Nutzung,
kommerziell lizenzpflichtig – siehe https://cheerpj.com/licensing/.
