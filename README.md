# Archipelago Modded

A Minecraft modpack for **NeoForge 1.21.1**, built around
[Create Aeronautics](https://modrinth.com/mod/create-aeronautics): airships,
boats and vehicles, plus Create tech, exploration and vanilla+ quality of life.
It is played on a dedicated server.

## Status

Planning. The mod list is drafted in [docs/MODLIST.md](docs/MODLIST.md); no
mods are installed yet.

## How it will work

- **[packwiz](https://packwiz.infra.link/)** keeps the pack as text files, one
  per mod, each with its download link and checksum. Mod jars are never
  committed.
- **Client:** a Prism Launcher instance runs packwiz-installer before every
  launch, so it always matches this repo.
- **Server:** the same pack, installed with the server-side mods only.
- Mods are added in four batches (keystone and performance, tech, world, QoL).
  Each batch is launched and its logs are checked before the next one goes in,
  because Sable (the physics library under Aeronautics) conflicts with many
  mods.

## Credits

See [CREDITS.md](CREDITS.md).
