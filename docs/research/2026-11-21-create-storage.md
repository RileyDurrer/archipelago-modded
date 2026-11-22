# Storage that plays well with Create

Researched 2026-11-21 for NeoForge 1.21.1, Create 6.0.10, Create Aeronautics
1.3.x and Sable 2.0.6. Goal: storage that is physical and built with Create,
not abstract digital storage. Marked **Inferred** where a source did not
confirm it. Nothing here was tested in game.

Create's mechanics below come from its own in-game Ponder and GUI text and
config in the 6.0.10 source
([lang file](https://github.com/Creators-of-Create/Create/blob/mc1.21.1-6.0.10/src/generated/resources/assets/create/lang/en_us.json),
[`CLogistics.java`](https://github.com/Creators-of-Create/Create/blob/mc1.21.1-6.0.10/src/main/java/com/simibubi/create/infrastructure/config/CLogistics.java)).
The Create fandom wiki refused automated reads.

## Create 6's own storage and logistics

- **Item vaults:** multiblock storage, 20 stacks per block by default. Only
  funnels, chutes and arms can reach inside, not players by hand.
- **Packager:** boxes a container's items into addressed cardboard packages,
  and unpacks packages fed back in.
- **Stock link:** joins a packager's container to a network.
- **Stock Ticker / Stock Keeper:** a mob or blaze burner seated at a stock
  ticker opens one searchable list of everything on the network. Players order
  from it and the items arrive as packages. Search can sync with JEI.
- **Delivery:** chain conveyors carry packages; frogports catch the ones
  addressed to them; postboxes at train stations send packages by train.
- **Automation:** factory gauges keep an item in stock by sending ingredients
  to factories the players build. Nothing plans multi-step crafts on request
  the way AE2 does. **Inferred** from the Ponder text.
- **Open dupes in 6.0.10:** the re-packager and factory-gauge crafting
  ([Create #8082](https://github.com/Creators-of-Create/Create/issues/8082),
  #8046, #8155).

## On airships

Older frogport and chain-conveyor crashes on ships are fixed
([Sable #319](https://github.com/ryanhcode/sable/issues/319)), but several
reports are still open:

- A frogport on a ship can move packages from any distance
  ([Aeronautics #1458](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/1458)).
- A frogport rendering crash ([Sable #1512](https://github.com/ryanhcode/sable/issues/1512)).
- Packages vanishing on belts that are part of a ship
  ([Aeronautics #1077](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/1077)).
- Factory gauge settings scrambled on assembly
  ([Aeronautics #955](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/955)).
- A locked Stock Keeper on a ship becomes open to everyone
  ([Aeronautics #1366](https://github.com/Creators-of-Aeronautics/Simulated-Project/issues/1366)).

**Inferred:** keep the logistics network on the ground; ships carry vaults or
chests and unload at ground frogports or train postboxes.

AE2 also has open crash reports on Sable, for example on world save
([Sable #1222](https://github.com/ryanhcode/sable/issues/1222)).

## Add-ons chosen (Riley, 2026-11-21)

| Mod | Why |
|---|---|
| [Create: Additional Logistics](https://modrinth.com/mod/create-additional-logistics) | Stops factory gauges flooding the network |
| [Create: Re-Packager Fix](https://modrinth.com/mod/create-re-packager-fix) | Patches the re-packager dupe until Create does |
| [Create: Vibrant Vaults](https://modrinth.com/mod/create-vibrant-vaults) | Vault styles and colour-coded logistics blocks |
| [Storage Drawers](https://modrinth.com/mod/storagedrawers) | Simple storage for players who struggle with Create. Create funnels work with it ([StorageDrawers #1214](https://github.com/jaquadro/StorageDrawers/issues/1214)). Bases only, because of render and lag bugs on ships ([Sable #178](https://github.com/ryanhcode/sable/issues/178), [#761](https://github.com/ryanhcode/sable/issues/761)) |

## Considered, not chosen

- **Create: Mobile Packages** (Robo Bees that deliver orders to players):
  optional, not picked yet.
- **Create: Connected:** large; its item silo duped items on ship assembly
  ([Sable #799](https://github.com/ryanhcode/sable/issues/799)).
- **Functional Storage:** beta and needs the Titanium library; Storage Drawers
  is the stable choice.
- **Create Stock Bridge:** joins AE2 and Create networks; only relevant if AE2
  stays.
