# Artifacts loot with our structure mods

Researched 2026-11-21 for NeoForge 1.21.1. Question: does Artifacts still put
its items in chests when YUNG's, Structory, When Dungeons Arise, Explorify and
Terralith replace or add structures? Marked **Inferred** where a source could
not confirm it.

## How Artifacts adds loot

- It injects loot only into specific vanilla loot tables, using NeoForge global
  loot modifiers that match one exact table ID each
  (`common/src/generated/resources/data/artifacts/loot_modifiers/inject/` on
  the 1.21.1 branch of [ochotonida/artifacts](https://github.com/ochotonida/artifacts)).
- Chest tables targeted include `simple_dungeon`, `abandoned_mineshaft`,
  `stronghold_corridor`, `desert_pyramid`, `jungle_temple`, `nether_bridge`,
  `shipwreck_treasure`, `buried_treasure`, `woodland_mansion`, `end_city_treasure`,
  bastions, ancient cities and most village chests. Not `stronghold_crossing`
  or `stronghold_library`.
- A modded table that nests a vanilla table does not get the loot: NeoForge
  applies modifiers by the outer table's ID (NeoForge 1.21.1
  `LootTable.java.patch`). **Inferred** from that patch plus vanilla's nested
  table code, which was not re-read.
- The maintainer confirms YUNG's mods use custom tables, so they don't get
  Artifacts loot by default ([artifacts #212](https://github.com/ochotonida/artifacts/issues/212)).

## By structure mod

Found by reading the loot table names in each mod's structure files and code
(1.21.1 branches of the [YUNG-GANG](https://github.com/YUNG-GANG) repos;
Stardust Labs repos for Structory and Terralith).

| Mod | Artifacts in its chests? | Detail |
|---|---|---|
| YUNG's Better Mineshafts | **Yes** | Every chest uses the vanilla mineshaft table |
| YUNG's Better Jungle Temples | **Partly** | Room and stair chests are vanilla; treasure chests are not |
| YUNG's Better Desert Temples | **Partly** | Some chests are vanilla, and suspicious sand uses vanilla archaeology |
| YUNG's Better Dungeons | **Partly** | Small dungeons only; skeleton, zombie, spider and nether dungeons are custom |
| YUNG's Better Strongholds | **Rarely** | A few corridor-table chests; most are custom |
| YUNG's Better Nether Fortresses | **Rarely** | About 1 in 10 chest entries is vanilla |
| YUNG's Better Ocean Monuments, Witch Huts | No | Custom tables only |
| Structory | No | Custom tables only. **Inferred** for 1.21.1: the repo has a 1.20 branch only |
| Terralith | **A few** | Two chests and its archaeology spots use vanilla tables. **Inferred** for 1.21.1 |
| When Dungeons Arise | **Probably no** | No public source. A separate "Loot Integrations" add-on exists to put modded loot in its chests ([CurseForge](https://www.curseforge.com/minecraft/mc-mods/loot-integrations-when-dungeons-arise)). **Inferred** |
| Explorify | Unknown | No public source found |

## Sources that don't need chests

From the 1.21.1 branch of Artifacts:

- **Campsites with mimics.** Artifacts' own underground camps spawn in every
  overworld biome (`biome_modifier/add_campsite.json`, tag
  `#minecraft:is_overworld`). Terralith adds its biomes to that tag
  (**Inferred** for 1.21.1). A killed mimic always drops an artifact.
- **Mob equipment.** Rare: zombies, skeletons, piglins and others can spawn
  wearing one.
- **Archaeology.** Works in Better Desert Temples and Terralith, which use the
  vanilla archaeology tables.
- **Everlasting Beef.** A rare drop from cows.

## What it means for the pack

Artifacts will turn up, but unevenly. Campsites, mineshafts, small dungeons,
temples and vanilla-table structures (shipwrecks, mansions, villages, bastions,
End cities) carry it. Most YUNG's rooms, Structory, and probably When Dungeons
Arise do not. To spread it wider, a small datapack could add Artifacts' loot
tables to those structures' tables. Undecided.
