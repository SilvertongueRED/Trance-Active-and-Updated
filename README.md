# Trance (Active and Updated)

A colour and font manager for Balatro. Pick a palette and a font and the whole game recolours, from the splash screen to blinds, suits, hand levels and the UI.

This is a maintained fork of [SpectralPack/Trance](https://github.com/SpectralPack/Trance). It stays in step with the parent and adds fixes and extras on top. As of v1.2.0 the parent has no commits newer than the one this fork is based on (`3f86c2e`).

## What this fork adds

| Version | Change |
| --- | --- |
| 1.2.0 | The **Trance** button is added to the options (pause) menu whether or not Steamodded is loaded. The parent only added it when Steamodded was absent. |
| 1.2.0 | The Trance screen opened from that button gets its tab as a function, which is what the game expects. |
| 1.2.0 | New palette: **Third Street Saints**. |
| 1.2.0 | Release workflow that builds and attaches the install zip. |

See [release-notes](release-notes) for the full notes of each release.

## Requirements

- Balatro
- [Lovely](https://github.com/ethangreen-dev/lovely-injector) (required, Trance patches the game through it)
- Steamodded is optional. Trance works without it.

## Install

1. Download `Trance-vX.Y.Z.zip` from the [Releases](https://github.com/SilvertongueRED/Trance-Active-and-Updated/releases) page.
2. Extract it into `%AppData%\Balatro\Mods\` so the file `Mods\Trance\trance.lua` exists. Do not nest the folder (no `Mods\Trance\Trance\`). Trance looks for the folder that holds `trance.lua`, so the folder name itself can differ, but it must be directly inside `Mods`.
3. Start the game.

## Use

- **Options menu:** open the options (pause) menu, in a run or from the main menu, and press the **Trance** button at the bottom of the list. It opens a screen with a **Selected Palette** picker and a **Selected Font** picker.
- **With Steamodded:** the mod also registers a config tab for Trance, so the same pickers are meant to be reachable from the Mods menu.

Your choice is saved to `%AppData%\Balatro\config\Trance.lua`, outside the mods folder, so updating or reinstalling the mod keeps it. If a saved palette or font file is missing or broken, Trance falls back to the defaults (Base Game and m6x11).

## Palettes

Base Game, CODE, Coonie's Theme, Dark Red, Jevil, Mule, Pastel, Planet, Queen, Simple Blue, Spooky, Third Street Saints, Trans

## Fonts

Bahnschrift, Calibri, Century Gothic, Comic Sans, Futura, Monogram, Noto Sans, Segoe, m3x6, m5x7, m6x11

## Add your own

**Palette:** copy `colors/Base Game.lua`, rename it (the file name becomes the name shown in the picker), and change the `HEX('RRGGBB')` values. Any colour you leave out keeps the Base Game value. Restart the game to see a new file in the list.

**Font:** put a `.ttf` in `fonts/` and a `.lua` with the same name next to it. Copy `fonts/m6x11.lua` as a starting point and tune `render_scale`, `TEXT_OFFSET`, `FONTSCALE` and the other values until the text sits right.

## How it works

`lovely.toml` appends `trance.lua` to the game's `main.lua` and patches the places where the game hard-codes colours (splash screen, Plasma Deck, chip and mult UI). At start-up Trance loads the Base Game palette, layers your chosen palette on top, and eases the game's colour tables toward it when you switch.

## Releasing (maintainers)

Bump `version` in `manifest.json`, add `release-notes/vX.Y.Z.md`, push to `main`, then run the **Release** workflow from the Actions tab. It zips the mod as `Trance/` and publishes `Trance-vX.Y.Z.zip` with the notes.

## Credits

- [lmesh91](https://github.com/lmesh91): original mod and overhaul
- MathIsFun0, crimsonseraphim, GayCoonie, someone23832 and avandemortel2137: parent contributions, palettes and fonts
- Ruby (lord-ruby): latest parent update
- SilvertongueRED: this fork

Trance is a SpectralPack project. See the parent repository for its licence and history.
