# Changelog

## 1.1.0 - 2026-09-30

- Dynasty hub and Create-a-Player menus are now raised in every version
  (`CFMHubRenderSettings`, `CreatePlayerRenderSettings` RenderFPS). They load their own
  render settings (30 on Low/VeryLow, 60 above, ignoring the user frame-rate setting),
  so they stayed choppy with earlier versions.
- 120 and 999 versions also raise `FrontEndRenderSettings` (the second settings asset
  the main menu loads; 60 on every tier in vanilla).
- New `999FPSMenus.fbmod` — menus effectively uncapped.
- Gameplay, in-game cutscene and story-scene render settings are still untouched.

## 1.0.3 - 2026-09-26

- Rebuilt both `.fbmod` files against the September 26, 2026 title update from
  fresh game data. Same single edit (`FrontEnd3DRenderSettings` RenderFPS); no
  functional changes.

## 1.0.2 - 2026-09-10

- Rebuilt both `.fbmod` files against the September 10, 2026 title update from
  fresh game data, so the mod carries no stale asset data from the previous update.
  Same single edit (`FrontEnd3DRenderSettings` RenderFPS); no functional changes.

## 1.0.1 - 2026-09-03

- Rebuilt both `.fbmod` files against the September 3, 2026 title update. The
  front-end cap is unchanged in this update (`FrontEnd3DRenderSettings` RenderFPS is
  still 30 on VeryLow..Ultra, 60 on SuperUltra, and the front end still ignores the
  user frame-rate setting), so the fix is the same single edit — re-exported from
  fresh game data so the mod carries no stale asset data from Title Update 3.5.
- Added a 120 FPS icon (`icon_120.png`) for the 120 FPS version.
- No functional changes.

## 1.0 - 2026-08-28

- Initial release. Restores 60 FPS front-end/menus (Title Update 3.5 locked them
  to 30 FPS on all quality levels except SuperUltra). Single EBX value edit:
  `global/RenderSettings/FrontEnd3DRenderSettings` RenderFPS 30 → 60 on
  VeryLow/Low/Medium/High/Ultra. No gameplay or online changes.
- Also ships a 120 FPS version (`120FPSMenus.fbmod`) for high-refresh monitors —
  same edit with all tiers set to 120. Install one or the other, not both.
