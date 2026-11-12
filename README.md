# GrowMate Strains

Open data for every strain in [GrowMate](https://www.growmate.gg/), the free weed growing and strain breeding game for Discord and the web.

* **140+ strains**: 126 in the two breeding trees (Indica and Sativa), plus player-made Mythics and season strains, added automatically as players create them
* Rarity from Common to Mythic
* Full breeding recipes: every hybrid lists its two parents
* Grow time, yield, XP, sell value, effects and flavors

## Files

| File | Description |
| --- | --- |
| [`data/strains.json`](data/strains.json) | All strains as JSON: `{ source, license, attribution, count, strains: [...] }` |
| [`data/strains.csv`](data/strains.csv) | The same data as CSV (effects and flavor are separated by `; `) |
| [`docs/`](docs/) | Player handbook, also published on GitBook |

The live, always current version is served from the GrowMate website (CORS enabled):

```
https://www.growmate.gg/strains/data/strains.json
https://www.growmate.gg/strains/data/strains.csv
```

## Example

```js
const res = await fetch('https://www.growmate.gg/strains/data/strains.json');
const { strains } = await res.json();

// Every recipe that produces a Mythic strain
const mythics = strains.filter((s) => s.rarity === 'mythic' && s.category === 'base' && s.parent_a);
console.log(mythics.map((s) => `${s.parent_a} x ${s.parent_b} = ${s.name}`));
```

## Fields

| Field | Type | Meaning |
| --- | --- | --- |
| `id` | string | Stable strain ID (also the URL slug: `growmate.gg/strains/<id>`) |
| `name` | string | Display name |
| `rarity` | string | `common`, `uncommon`, `rare`, `epic`, `legendary`, `mythic` |
| `type` | string | `indica`, `sativa` or `hybrid` |
| `parent_a`, `parent_b` | string or null | Breeding parents, null for seed strains |
| `grow_hours` | number | Hours from planting to harvest |
| `yield_g` | number | Grams per harvest |
| `xp` | number | XP earned per harvest |
| `coins` | number | Base sell value in game coins |
| `effects`, `flavor` | string[] | Listed effects and flavors |
| `category` | string | `base` (breeding tree strain), `player_made` (custom Mythic named by a player) or `season` (limited season strain) |
| `creator` | string or null | Username of the player who created a `player_made` strain |

## License

The data in this repository is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please credit **GrowMate** and link to https://www.growmate.gg/strains.

These are in-game strains from a video game. Stats like grow time and yield describe gameplay, not real plants.

## Links

* Play: [growmate.gg](https://www.growmate.gg/)
* Strain database: [growmate.gg/strains](https://www.growmate.gg/strains)
* Genetics chart: [growmate.gg/strains/genetics](https://www.growmate.gg/strains/genetics)
* Breeding guide: [growmate.gg/guides/breeding](https://www.growmate.gg/guides/breeding)
* Add the Discord bot: [growmate.gg/install](https://www.growmate.gg/install)
* Community: [discord.gg/k2CzuXqmSc](https://discord.gg/k2CzuXqmSc)
