# CFB 27 — 60 FPS Menus

Uncaps the **menus** in EA Sports College Football 27 on PC: **60**, **120** or
**999 (unlocked)** FPS.

Title Update 3.5 (2026-08-27) locked the front end — main menu, team select, settings
screens — to **30 FPS** at every graphics quality level except SuperUltra, and the
Dynasty hub and Create-a-Player scenes have their own cap (30 on Low/VeryLow, 60
above). The game's own frame-rate setting does not help, because all of these menus
are explicitly flagged to ignore the user frame-rate setting. This mod raises every
menu render target to the version you pick.

## What it changes (exactly)

One value (`RenderFPS`) in the menu render-settings assets — nothing else:

| Asset | Used by | Vanilla (VeryLow … SuperUltra) |
|---|---|---|
| `global/RenderSettings/FrontEnd3DRenderSettings` | main menu, Edit Avatar | 30 30 30 30 30 60 |
| `ContentShared/global/RenderSettings/FrontEndRenderSettings` | main menu, Edit Avatar | 60 on every tier |
| `ContentShared/global/RenderSettings/CFMHubRenderSettings` | Dynasty hub | 30 30 60 60 60 60 |
| `ContentShared/global/RenderSettings/CreatePlayerRenderSettings` | Create-a-Player | 30 30 60 60 60 60 |

Each version sets every tier of these to its number (the 60 version leaves
`FrontEndRenderSettings` alone, since it is already 60).

The `IgnoreRenderFpsUserSettings = true` flags are kept, so the menu frame rate is
pinned to the chosen value regardless of the in-game frame-rate limit. **Gameplay,
in-game cutscenes and story scenes are not touched**, and no game logic changes.

## Three versions — pick ONE

- **`60FPSMenus.fbmod`** — every menu at 60 FPS.
- **`120FPSMenus.fbmod`** — every menu at 120 FPS, for high-refresh monitors.
- **`999FPSMenus.fbmod`** — every menu effectively uncapped. Menus render as fast as
  your GPU allows, so expect higher GPU load and heat while sitting in menus; use your
  GPU driver's frame limiter if you want a specific number.

Install only one of the three.

## Install

1. Download `60FPSMenus.fbmod`, `120FPSMenus.fbmod` **or** `999FPSMenus.fbmod` from the [latest release](../../releases/latest).
2. Open **MMC Mod Manager**, import the `.fbmod`, enable it.
3. Launch the game through the Mod Manager. If you are upgrading from an older
   version, remove it first and use **Delete ModData and Launch** once.

Requires [MMC Editor / Mod Manager](https://discord.gg/maddenmoddingcommunity) for
College Football 27. Like all MMC mods, playing modded means playing offline.

## After a title update

**Current build: v1.1.1, built for the October 1, 2026 title update.**

Title updates reset/patch game data, and the mod may need a rebuild against the new
data. The MMC project file (`UncappedMenuFPS.fbproject`) is included — open it in
MMC Editor after an update, verify the RenderFPS values on the assets above, and
re-export.

## License

MIT — see [LICENSE](LICENSE).
