# CFB 27 — 60 FPS Menus

Restores **60 FPS menus** in EA Sports College Football 27 on PC.

Title Update 3.5 (2026-08-27) locked the entire front end — main menu, Dynasty hub,
Road to Glory hub, team select, settings screens — to **30 FPS** at every graphics
quality level except SuperUltra. The game's own "uncapped" frame-rate setting does
not help, because the front end is explicitly flagged to ignore the user frame-rate
setting. This mod raises the front-end render target back to 60 FPS at every quality
level, matching how the menus behaved before the update.

## What it changes (exactly)

One value in one asset — nothing else:

- `global/RenderSettings/FrontEnd3DRenderSettings` → `RenderFPS`:
  `VeryLow/Low/Medium/High/Ultra` raised **30 → 60** (SuperUltra was already 60) —
  or all six tiers set to **120** in the 120 FPS version.

The front end keeps its `IgnoreRenderFpsUserSettings = true` flag, so menus are
pinned at 60 exactly like they were pre-update — this mod does not touch gameplay,
cutscenes, or any other render state, and changes no game logic. In-game behaviour
(including online) is unchanged.

## Two versions — pick ONE

- **`60FPSMenus.fbmod`** — menus at 60 FPS, exactly like before Title Update 3.5.
- **`120FPSMenus.fbmod`** — menus at 120 FPS, for high-refresh monitors. Same single
  value, set to 120 instead of 60.

The menu frame rate is pinned to the chosen value regardless of the in-game frame
rate limit setting (the front end ignores that setting by design). Install only one
of the two.

## Install

1. Download `60FPSMenus.fbmod` **or** `120FPSMenus.fbmod` from the [latest release](../../releases/latest).
2. Open **MMC Mod Manager**, import the `.fbmod`, enable it.
3. Launch the game through the Mod Manager.

Requires [MMC Editor / Mod Manager](https://discord.gg/maddenmoddingcommunity) for
College Football 27. Like all MMC mods, playing modded means playing offline.

## After a title update

**Current build: v1.0.2, rebuilt for the September 10, 2026 title update.** (Neither
September update changed the front-end cap — the same edit still applies.)

Title updates reset/patch game data, and the mod may need a rebuild against the new
data. The MMC project file (`UncappedMenuFPS.fbproject`) is included — open it in
MMC Editor after an update, verify the RenderFPS values on
`global/RenderSettings/FrontEnd3DRenderSettings`, and re-export.

## License

MIT — see [LICENSE](LICENSE).
