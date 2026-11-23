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

## Booster-Rezepte (Magic)

Der Magic-Adapter öffnet jedes Set mit seinem echten Rezept: `provider.booster_source` zeigt auf
[MTGJSON](https://mtgjson.com) (eine Datei pro Set, wird beim ersten Pack geladen). Für Sets, die
MTGJSON noch nicht führt, greifen die `booster_eras` nach Erscheinungsdatum (Näherungen über
Raritäten-Quoten, keine Druckbögen):

| ab | Pack | Regel |
|---|---|---|
| – | Booster | 15 Karten, keine Foils |
| 1999-02-15 | Draft Booster | 15 Karten, in jedem dritten Pack ersetzt ein Foil eine Common |
| 2024-02-09 | Play Booster | 14 Karten, ein Foil garantiert |
| 2027-02-05 | Booster Pack | 14 Karten, kein garantierter Foil, Foils nur Rare/Mythic; 1 von 1.000 Packs ist ein God Pack (14 Rares/Mythics) |

Die 2027er-Regel folgt der Ankündigung von Wizards vom 2026-10-05 und gilt ab „Nauctis: The Sunken
Realm". **Annahmen**, bis MTGJSON die echten Rezepte führt:

- Wizards nennt keine Quote für den Foil-Rare-Slot; der Adapter rechnet mit einem Foil in jedem
  vierten Pack.
- God Packs kündigt Wizards für Magic-Multiverse-Sets an, Universes Beyond „voraussichtlich 2028".
  Ob Universes-Beyond-Sets 2027 schon ohne Foil-Commons erscheinen, steht dort nicht — sie stehen
  in `except` und bleiben beim Play Booster.
- Die God-Pack-„Celebration"-Karte fehlt (es gibt sie in keinem Katalog); das God Pack hat 14
  Rares/Mythics, zwei davon Foil.

Status: WIP — Schema wird mit #145 (Datenprofile, Booster-Sheets, Preise) ausgebaut.
Der Ordnername eines Adapters ist seine Identität (Save-Bindung) — nie umbenennen.
