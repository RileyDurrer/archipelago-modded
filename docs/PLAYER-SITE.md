# Player download site and install flow (plan)

Written 2026-11-21. Planning only: nothing here is built yet. Claims are cited;
anything marked **Guess** or **To test** has not been confirmed.

## Goal

Players can get into the server with as few steps and decisions as possible.
Some players are not confident with launchers or written instructions, so the
site is built around one button, screenshots and a "stuck?" contact, and the
install should work if a player clicks through every screen with the defaults.

## Decisions (Riley, 2026-11-21)

- **Launcher: Prism Launcher with packwiz-installer.** Players use a mix of
  launchers today. Prism was chosen because packwiz-installer runs before every
  launch and keeps the player's mods matching the server with no clicks, which
  removes the "wrong mod version" errors these players would struggle to fix.
- **Optional client mods: all on by default.** Players who want to turn one
  off can; that is up to them. Clicking through with the defaults always gives
  the full, supported setup.
- **No mod picker on the website.** Choosing happens in packwiz-installer's
  own dialog. A website picker would need a backend to build per-player zips
  and a second copy of the optional-mod list to keep in sync.

## How players install (target flow)

1. Install Prism Launcher (link to prismlauncher.org/download).
2. Sign in with their Microsoft account in Prism.
3. Download `Archipelago.zip` from the site (the one big button).
4. In Prism: **Add Instance → Import**, choose the zip. Prism's import page
   supports zip and mrpack files ([Prism wiki: Import](https://prismlauncher.org/wiki/help-pages/zip-import/)).
5. Click **Play**. The first launch downloads the mods, then the game opens.

Updates need nothing from the player: the installer syncs on every launch.

**To test:** whether dragging the zip onto the Prism window also imports it
(not found in the wiki). If it works, step 4 becomes "drag the file onto Prism".

## How the instance zip works

- The zip is a Prism instance with `packwiz-installer-bootstrap.jar` in the
  instance's Minecraft folder (the folder with `options.txt`) and a pre-launch
  command set under Edit Instance → Settings → Custom commands:
  `"$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://<site>/pack.toml`
  ([packwiz: packwiz-installer tutorial](https://packwiz.infra.link/tutorials/installing/packwiz-installer/);
  the page is written for MultiMC, which Prism is forked from).
- The site hosts `pack.toml`, `index.toml` and the `mods/*.pw.toml` files as
  static files. Mod jars are not hosted: each `.pw.toml` points at the mod's
  own Modrinth or CurseForge download.
- The server installs from the same `pack.toml` with `-g -s server`, which
  downloads only mods whose side is `both` or `server` (same tutorial).

## Optional client mods

A mod is made optional in its `.pw.toml`
([packwiz: mod toml reference](https://packwiz.infra.link/reference/pack-format/mod-toml/)):

```toml
side = "client"

[option]
optional = true
default = true
description = "Shown to players in the optional-mods dialog."
```

How packwiz-installer behaves, from its source (`UpdateManager.kt`,
`DownloadTask.kt` in [packwiz-installer](https://github.com/packwiz/packwiz-installer)):

- On a first install, or when an optional mod is new to the pack, the full
  selection dialog opens, pre-ticked with each mod's `default`.
- On every other launch, a short timed prompt asks whether to reconfigure
  optional mods; doing nothing continues the launch. That timed screen on
  every launch is confirmed in
  [packwiz-installer #93](https://github.com/packwiz/packwiz-installer/issues/93).
- Choices are stored in the installer's local manifest file in the instance.
  No reset flag is documented. **Guess:** deleting that manifest makes the
  next launch act like a first install. **To test.**
- Known bug, open since 2025-12-24 ([#93](https://github.com/packwiz/packwiz-installer/issues/93)):
  a mod with `default = false` was installed anyway. It does not affect this
  pack while every optional mod defaults to on.

Candidate optional mods (all client-only; server-required mods such as Create,
Aeronautics, Sable and Waterworks cannot be optional):

| Mod | Why a player might turn it off |
|---|---|
| Iris | Open Aeronautics report of a visual glitch with shaders |
| Sodium | Open Aeronautics report of a vertex glitch |
| Xaero's Minimap, Xaero's World Map | Open report of a loading-screen hang with Sable ([Sable #1109](https://github.com/ryanhcode/sable/issues/1109)) |
| Mouse Tweaks, Controlling, AppleSkin, Jade | Personal preference |

Entity Culling and ImmediatelyFast stay required: they are performance mods
players have no reason to remove.

## Java

Minecraft 1.21.1 needs Java 21. Prism 9.0+ can download and pick Java itself
([Prism 9.0 release](https://prismlauncher.org/news/release-9.0)), using
"Autodetect Java version" and "Auto-download Mojang Java" under Settings →
Java ([Prism wiki: Installing Java](https://prismlauncher.org/wiki/getting-started/installing-java/)).
The downloader is not in every Linux package (the wiki names the Flatpak and
AppImage as having it).

**To test:** whether these are on by default on a fresh Prism install, and
whether the instance zip can carry the setting so players never see a Java
error. If neither works, the guide needs a screenshot step for these two
checkboxes.

## The website

- **One page, one big download button** for the instance zip.
- **The five steps above, each with a screenshot**, plus a short screen
  recording of the whole install.
- **A "stuck?" line** naming who to message; a friend on a call beats any
  written guide.
- A small "Change optional mods" section: what the reconfigure prompt looks
  like and which mods are safe to turn off.
- **Hosting: not decided.** Options are Caddy on the home server (where the
  game server already runs) or GitHub Pages. Either serves static files only.

## Open questions

- Hosting: home server Caddy or GitHub Pages.
- Accounts: **Guess** that each player needs their own Microsoft account
  that owns Minecraft Java to join the server (Prism's FAQ does not say).
  Whether every player has one is not checked.
- The four **To test** items above, to run with a two-mod test pack before
  the full pack goes up.
