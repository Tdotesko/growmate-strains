# Strain Data (free download)

Every GrowMate strain is available as open data under **CC BY 4.0**: the 126 breeding tree strains plus every player-made and season strain, added automatically as players create them. Use it for fan sites, wikis, Discord bots, spreadsheets, calculators or anything else.

## Download

* JSON: [growmate.gg/strains/data/strains.json](https://www.growmate.gg/strains/data/strains.json) (CORS enabled, refreshed every 10 minutes)
* CSV: [growmate.gg/strains/data/strains.csv](https://www.growmate.gg/strains/data/strains.csv)
* GitHub: [Tdotesko/growmate-strains](https://github.com/Tdotesko/growmate-strains) (snapshot in `data/`)
* About the dataset: [growmate.gg/strains/data](https://www.growmate.gg/strains/data)

## Fields

The JSON file is an object with `source`, `license`, `attribution`, `count` and a `strains` array. Each strain has these fields:

| Field | Type | Meaning |
| --- | --- | --- |
| `id` | string | Stable strain ID, also used in the strain page URL |
| `name` | string | Display name |
| `rarity` | string | common, uncommon, rare, epic, legendary or mythic |
| `type` | string | indica, sativa or hybrid |
| `parent_a` | string or null | First breeding parent, null for seed strains |
| `parent_b` | string or null | Second breeding parent, null for seed strains |
| `grow_hours` | number | Hours from planting to harvest |
| `yield_g` | number | Grams harvested per plant |
| `xp` | number | XP earned per harvest |
| `coins` | number | Base sell value in game coins |
| `effects` | string[] | Listed effects |
| `flavor` | string[] | Listed flavors |
| `category` | string | base (breeding tree strain, counted in the Growdex), player_made (custom Mythic named by a player) or season (limited season strain) |
| `creator` | string or null | Username of the player who created a player_made strain |

Field names are stable. New fields may be added at the end, but existing ones won't be renamed or removed.

## Attribution

Please credit **GrowMate** with a link to [https://www.growmate.gg/strains](https://www.growmate.gg/strains), for example:

> Strain data from [GrowMate](https://www.growmate.gg/strains), CC BY 4.0.
