# Tweak-Mods (#141)

Gameplay-Mods über exponierte Spiel-Variablen: ein Ordner pro Mod mit
`tweaks.json`. Installiert wird wie bei Adaptern nach `user://mods/<ordner>/`
(Ordnername = Identität), an/aus über denselben Mods-Schalter im Spiel.

## Manifest

```json
{
  "name": "God Mode (Tweak)",
  "seed_version": 1,
  "min_app_version": "0.1",
  "tweaks": { "<id>": <wert> }
}
```

## Allowlist (Registry v1 — nur diese IDs, keine freien Property-Pfade)

| id | Typ | balance_relevant | Wirkung |
|---|---|---|---|
| `gold_multiplier` | Faktor | ja | multipliziert jeden Gold-VERDIENST |
| `pack_price_multiplier` | Faktor | ja | multipliziert Pack-Preise (0 = gratis) |
| `divider_price_multiplier` | Faktor | ja | multipliziert Trennseiten-Preise |
| `tincture_time_multiplier` | Faktor | ja | streckt/kürzt die Tinktur-Einwirkzeit |
| `currency_name` | String oder `{en,de}` | nein | benennt die Währung um (überall via `{currency}`) |
| `currency_icon` | Pfad relativ zum Mod-Ordner | nein | ersetzt das Münz-Icon überall |

Der erste aktive balance-relevante Tweak stempelt das Save dauerhaft als
`modded_economy` — auch nach dem Deaktivieren. Unbekannte IDs werden im
Mods-Panel als Fehler angezeigt, nie geraten.
