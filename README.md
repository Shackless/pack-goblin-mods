# Pack Goblin Mods

Adapter- und Tweak-Mods für [Pack Goblin](http://git.lan/Shackles/pack-goblin) — die Mod-Plattform (#140/#145).

- **`adapters/`** — ein Ordner pro Spiel-Adapter: `game.json` im Mod-Manifest-Format
  (siehe `docs/modding.md` im Hauptrepo). Nur Konfiguration + öffentliche API-URLs,
  **niemals Assets/Kartenbilder** — die lädt der Client von den öffentlichen Quellen.
- **`tweaks/`** — Gameplay-Mods (exponierte Spiel-Variablen, #141). Schema folgt.
- **`index.json`** — der Katalog, den der In-Game-Mod-Browser lädt (eine Datei, ein Fetch).
  Bezug per Raw-URL: `http://git.lan/pack-goblin/mods/raw/branch/main/index.json` —
  dasselbe Konzept funktioniert nach einem späteren GitHub-Spiegel (raw/Pages) unverändert.

Status: WIP — Schema wird mit #145 (Datenprofile, Booster-Sheets, Preise) ausgebaut.
Der Ordnername eines Adapters ist seine Identität (Save-Bindung) — nie umbenennen.
