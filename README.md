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
  `VeryLow/Low/Medium/High/Ultra` raised **30 → 60** (SuperUltra was already 60).

The front end keeps its `IgnoreRenderFpsUserSettings = true` flag, so menus are
pinned at 60 exactly like they were pre-update — this mod does not touch gameplay,
cutscenes, or any other render state, and changes no game logic. In-game behaviour
(including online) is unchanged.

## Install

1. Download `60FPSMenus.fbmod` from the [latest release](../../releases/latest).
2. Open **MMC Mod Manager**, import the `.fbmod`, enable it.
3. Launch the game through the Mod Manager.

Requires [MMC Editor / Mod Manager](https://discord.gg/maddenmoddingcommunity) for
College Football 27. Like all MMC mods, playing modded means playing offline.

## After a title update

Title updates reset/patch game data, and the mod may need a rebuild against the new
data. The MMC project file (`UncappedMenuFPS.fbproject`) is included — open it in
MMC Editor after an update, verify the RenderFPS values on
`global/RenderSettings/FrontEnd3DRenderSettings`, and re-export.

## License

MIT — see [LICENSE](LICENSE).
