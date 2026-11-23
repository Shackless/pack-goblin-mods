# Pack Goblin Mods

Adapter- und Tweak-Mods für Pack Goblin, ein TCG-Booster-Opening-Spiel. Inoffizielles Fanprojekt:
nicht verbunden mit, gesponsert oder unterstützt von den Rechteinhabern der hier adaptierten Kartenspiele.

- **`adapters/`** — ein Ordner pro Spiel-Adapter: `game.json` im Mod-Manifest-Format
  (siehe `docs/modding.md` im Spiel-Repo). Nur Konfiguration + öffentliche API-URLs,
  **niemals Assets/Kartenbilder** — die lädt der Client von den öffentlichen Quellen.
- **`tweaks/`** — Gameplay-Mods (exponierte Spiel-Variablen, #141). Schema folgt.
- **`index.json`** — der Katalog, den der In-Game-Mod-Browser lädt (eine Datei, ein Fetch).
  Bezug per Raw-URL:
  `https://raw.githubusercontent.com/Shackless/pack-goblin-mods/main/index.json`.

Status: WIP — Schema wird mit #145 (Datenprofile, Booster-Sheets, Preise) ausgebaut.
Der Ordnername eines Adapters ist seine Identität (Save-Bindung) — nie umbenennen.
