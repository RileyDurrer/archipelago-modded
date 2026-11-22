# Archipelago Modded: mod list (planning)

Base: **NeoForge, Minecraft 1.21.1**. Themes: tech/automation, exploration, vanilla+.
Multiplayer: dedicated server on the home server.
Keystone: **Create Aeronautics**.
World: an **archipelago**, with no continents and no massive islands. Decided
2026-11-22: Tectonic stays on its default config, and Riley picks a seed with
the right island layout when the world is created. If no seed works, the
fallbacks are tuning Tectonic (Ocean Offset, Continents Scale, the Islands
settings) or Sky Archipelago (see Watchlist).

Started 2026-11-19. Versions and sides were checked against the Modrinth API on
2026-11-19 unless noted. This list is the pack's credit record until the mods
are installed (see [CREDITS.md](../CREDITS.md)).

Status key: **Batch N** = planned, added in build batch N · **Undecided** =
waiting on Riley · **Watchlist** = wanted, not ready yet · **Dropped** = decided
against (reason given).

## Planned

### Batch 1: keystone and performance
| Mod | Source | Version checked | Sides (client/server) | Licence | Notes |
|---|---|---|---|---|---|
| Create | Modrinth `create` | 6.0.10+mc1.21.1 | optional / required | Create Mod License | |
| Create Aeronautics (bundled: Simulated, Aeronautics, Offroad) | Modrinth `create-aeronautics` | 1.3.2+mc1.21.1 | required / required | Simulated Project License | Keystone |
| Sable | Modrinth `sable` | 2.0.6+mc1.21.1 | required / required | PolyForm Shield 1.0.0 | Required by Aeronautics. Its page warns it often conflicts with other mods |
| Waterworks | Modrinth `waterworks` | 1.2.2.1 | required / required | All Rights Reserved | Hides water inside hulls (water occlusion), plus sailing, waves, sinking |
| Sodium | Modrinth `sodium` | mc1.21.1-0.8.13-neoforge | required / unsupported | PolyForm Shield 1.0.0 | Open Aeronautics bug report: vertex glitch with Sodium. Test first |
| Iris | Modrinth `iris` | 1.8.14-beta.1 | required / unsupported | LGPL-3.0 | Open Aeronautics bug report: visual glitch with shaders. Test first |
| FerriteCore | Modrinth `ferrite-core` | 7.0.3-neoforge | optional / optional | MIT | |
| ModernFix | Modrinth `modernfix` | 5.27.27+mc1.21.1 | optional / optional | LGPL-3.0 | |
| Lithium | Modrinth `lithium` | mc1.21.1-0.15.4-neoforge | optional / optional | LGPL-3.0 | |
| Entity Culling | Modrinth `entityculling` | 1.12.1 | required / unsupported | tr7zw Protective License | |
| ImmediatelyFast | Modrinth `immediatelyfast` | 1.6.15+1.21.1-neoforge | required / unsupported | LGPL-3.0 | |
| spark | Modrinth `spark` | 1.10.124-neoforge-1.21.1 | optional / optional | GPL-3.0 | Server lag profiling |

### Batch 2: tech
| Mod | Source | Version checked | Licence | Notes |
|---|---|---|---|---|
| Applied Energistics 2 | Modrinth `ae2` | 19.2.20 | Multiple | Chosen over Refined Storage |
| Create Crafts & Additions | Modrinth `createaddition` | neoforge-1.21.1-1.7.2 | MIT | Electricity |
| Create: Enchantment Industry | Modrinth `create-enchantment-industry` | 2.5.4b | LGPL-3.0 | |
| Create: Copycats+ | Modrinth `copycats` | (latest 1.21.1) | | Light blocks for ship hulls |
| Create Big Cannons | Modrinth `create-big-cannons` | 5.11.7 (2026-06-22) | Create Big Cannons License | Airship combat. Needs Ritchie's Projectile Library (`rpl`, MIT). Many open crash reports with Aeronautics/Sable; must pass the cannon tests below or move to Watchlist |
| Ritchie's Projectile Library | Modrinth `rpl` | (latest 1.21.1) | MIT | Required by Big Cannons |
| Sophisticated Backpacks | Modrinth `sophisticated-backpacks` | 1.21.1-3.26.22.2257 | All Rights Reserved | |
| Sophisticated Storage | Modrinth `sophisticated-storage` | 1.21.1-1.6.20.2239 | All Rights Reserved | |

### Batch 3: world and exploration
| Mod | Source | Version checked | Licence | Notes |
|---|---|---|---|---|
| Terralith | Modrinth `terralith` | 2.6.2 | Stardust Labs License | Server-side world generation |
| Tectonic | Modrinth `tectonic` | 3.0.28-neoforge-21.1 | MIT | Server-side world generation |
| YUNG's Better Dungeons, Mineshafts, Strongholds, Desert Temples, Jungle Temples, Ocean Monuments, Nether Fortresses, Witch Huts | Modrinth `yungs-better-*` | 1.21.1-NeoForge (2024–25 builds) | LGPL-3.0 | Server-side; need YUNG's API |
| When Dungeons Arise | Modrinth `when-dungeons-arise` | 2.1.68 | All Rights Reserved | Includes sky dungeons, good airship targets |
| Explorify | Modrinth `explorify` | v1.6.6 | All Rights Reserved | |
| Structory | Modrinth `structory` | 1.3.17 | Stardust Labs License | |
| Nullscape | Modrinth `nullscape` | 1.2.14 | Stardust Labs License | |
| Aquamirae | Modrinth `aquamirae` | 7.2.13 | Obscuria Modding License | |
| Artifacts | Modrinth `artifacts` | 13.2.5 | MIT | |
| Naturalist | Modrinth `naturalist` | 2.0.7+1.21.1-neoforge | Custom | |

### Batch 4: vanilla+ / QoL
| Mod | Source | Version checked | Licence | Notes |
|---|---|---|---|---|
| JEI | Modrinth `jei` | 19.70.0.469 | MIT | Recipe viewer |
| Jade | Modrinth `jade` | 15.10.6+neoforge | CC-BY-NC-SA-4.0 | |
| Xaero's Minimap | Modrinth `xaeros-minimap` | neoforge-1.21.1-26.6.0 | All Rights Reserved | |
| Xaero's World Map | Modrinth `xaeros-world-map` | neoforge-1.21.1-1.47.0 | All Rights Reserved | |
| AppleSkin | Modrinth `appleskin` | 3.0.9+mc1.21 | Unlicense | |
| Mouse Tweaks | Modrinth `mouse-tweaks` | 1.21-2.26.1-neoforge | BSD-3-Clause | |
| Controlling | Modrinth `controlling` | 19.0.5 | MIT | |
| Carry On | Modrinth `carry-on` | 2.2.6 | LGPL-3.0 | |
| Carry On + Create Aeronautics Compat | Modrinth `carryon-aeronautics-compat` | (latest 1.21.1) | | Lets Carry On work on moving ships; server-side |
| Comforts | Modrinth `comforts` | 9.0.5+1.21.1 | LGPL-3.0 | |
| Polymorph | Modrinth `polymorph` | 1.2.0+1.21.1 | LGPL-3.0 | |
| GraveStone Mod | Modrinth `gravestone-mod` | neoforge-1.21.1-1.0.40 | All Rights Reserved | |
| Chunky | Modrinth `chunky` | 1.4.23 | GPL-3.0 | Pre-generate the world on the server |

### Cannon tests (batch 2)
Decided 2026-11-21: Big Cannons is in unless plain TNT cannons already work
well on ships. Research that day (bug trackers for Aeronautics and Sable)
showed neither is proven:

- **TNT on ships:** open reports that TNT moving on a ship and hitting blocks
  can freeze the server ([Aeronautics #1395](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/1395),
  [Sable #1510](https://github.com/ryanhcode/sable/issues/1510)), and that
  TNT explodes in water when it shouldn't ([Sable #193](https://github.com/ryanhcode/sable/issues/193)).
  No reports found about water/redstone TNT cannons specifically.
- **Big Cannons on ships:** many of the early crashes are closed, but open
  ones remain. Crash detonating high-explosive shells
  ([Sable #1657](https://github.com/ryanhcode/sable/issues/1657), 2026-11-05);
  crash when a shell destroys a ship
  ([Sable #1454](https://github.com/ryanhcode/sable/issues/1454)); cannons
  falling apart on ships ([Aeronautics #1429](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/1429));
  crash from explosions in unloaded chunks ([Sable #1412](https://github.com/ryanhcode/sable/issues/1412)).
- Add-ons built for using both together exist (armour blocks, shields), so
  people do play this combination.

Tests on the server in batch 2, each checked in the logs:
1. Place a cannon mount on a ship, assemble and fly it.
2. Fire solid shot and high-explosive shells from a moving ship.
3. Hit one ship with another ship's shell.
4. Build a plain TNT cannon on a ship and fire it, for comparison.

If 1–3 crash and 4 works, drop Big Cannons to the Watchlist and use TNT cannons.

## Undecided
| Mod | Source | Question |
|---|---|---|
| Create Aeronautics: Transmission & Linkage | Modrinth `create-aeronautics-transmission-linkage` | Extra vehicle parts: in or out? |

## Watchlist (wanted, not ready yet)
| Mod | Source | Checked | Why it's waiting | What would make it ready |
|---|---|---|---|---|
| **TownTopia** | CurseForge `towntopia` | 2026-11-20: v0.1.3, NeoForge 1.21.1, updated 2026-11-15, ~2.8k downloads, All Rights Reserved, needs GeckoLib | Very early alpha ("in active development"). CurseForge-only, and it's unknown whether the author allows automatic downloads (packwiz needs that for hands-off installs and the server). Untested with Sable | A more stable release, plus a confirmed automatic download when packwiz adds it. Goes in batch 4 |
| TownTopia: Additions | CurseForge (fan add-on by AnthonyS1337) | 2026-11-20 | Depends on TownTopia | Add after TownTopia works |
| TownTopia: Integrations | CurseForge (fan add-on by AnthonyS1337) | 2026-11-20 | Depends on TownTopia | Add after TownTopia works |
| Sky Archipelago | Modrinth `sky-archipelago` | 2026-11-22: v1.4 (2026-10-31), NeoForge 1.21.1 only, All Rights Reserved | Fallback world type if no Tectonic seed gives a good archipelago. Configurable island sizes, spacing and ocean layer; built for Aeronautics. Replaces terrain, so Tectonic would come out; unknown whether Terralith biomes survive | Only if seed hunting with default Tectonic fails |
| Aero Ship Buoyancy | Modrinth `aero-ship-buoyancy` | 2026-11-19: v1.4.0 | May overlap Waterworks' buoyancy | Only if Waterworks' buoyancy isn't enough |

## Dropped
| Mod | Reason |
|---|---|
| Mekanism | Open bug report of a rendering problem with Aeronautics/Sable; pulls play away from Create (Crafts & Additions covers power). Confirmed by Riley 2026-11-21 |
| Waystones | Airships make getting there the fun part. Confirmed by Riley 2026-11-21 |
| Refined Storage | Duplicates AE2 |
| Embeddium | Sodium now has a native NeoForge build |
| Inventory Profiles Next | Mouse Tweaks covers most of it |
| C2ME | Still alpha |
| Noisium | No update since 2024 |
| Sable Water Fix | Single release, ~1k downloads, code stated as AI-generated; too risky beside Sable |
| Alex's Mobs | No official 1.21.1 build |
| Archipelago (mod) | One 0.0.2 release from 2024; the author says it's untested with other mods |
| Aero Islands | Floating islands over void, no sea; would make Waterworks pointless |
| Storage Drawers, Repurposed Structures, L_Ender's Cataclysm, FTB Chunks | Not found on Modrinth under those names; check CurseForge if wanted |
