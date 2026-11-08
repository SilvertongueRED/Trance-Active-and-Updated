# Trance (Active and Updated)

A colour and font manager for Balatro. Pick a palette and a font and the whole game recolours, from the splash screen to blinds, suits, hand levels and the UI.

This is a maintained fork of [SpectralPack/Trance](https://github.com/SpectralPack/Trance). The parent repository was archived by its owner on Aug 24, 2026 and is read-only, so this fork is where fixes and additions now land, including the pull requests that were still open on the parent. The code is based on the parent's last commit (`3f86c2e`).

## What this fork adds

| Version | Change |
| --- | --- |
| 1.3.0 | New palette **OLED Friendly** (blacks out the chips and mult score boxes and the options button), from parent PR #10 by Chris Riker (rikercd). |
| 1.3.0 | New font **League Gothic**, from parent PR #11 by jack5github. League Gothic is licensed under the SIL Open Font License 1.1. |
| 1.2.1 | The options menu **Trance** button is compact, so the menu still fits on screen with many mods installed. |
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

Base Game, CODE, Coonie's Theme, Dark Red, Jevil, Mule, OLED Friendly, Pastel, Planet, Queen, Simple Blue, Spooky, Third Street Saints, Trans

## Fonts

Bahnschrift, Calibri, Century Gothic, Comic Sans, Futura, League Gothic, Monogram, Noto Sans, Segoe, m3x6, m5x7, m6x11

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
- Chris Riker (rikercd): OLED Friendly palette
- Jack5 (jack5github): League Gothic font
- SilvertongueRED: this fork

Trance is a SpectralPack project. See the parent repository for its licence and history.

---

<!-- other-mods:start -->
## More from SilvertongueRED

**Fit To Screen is now on Nexus Mods:** [nexusmods.com/balatro/mods/1001](https://www.nexusmods.com/balatro/mods/1001). It stops tall pause menus and sidebars from being cut off at the top and bottom of your screen.

### See my other mods and forks

- [Balatro-Fit-To-Screen](https://github.com/SilvertongueRED/Balatro-Fit-To-Screen) ([Nexus Mods](https://www.nexusmods.com/balatro/mods/1001)) - stops tall pause menus and sidebars from being cut off at the top and bottom of your screen
- [Balatro-Mod-Search-and-Sort](https://github.com/SilvertongueRED/Balatro-Mod-Search-and-Sort) ([Nexus Mods](https://www.nexusmods.com/balatro/mods/984)) - search, filter and sort the Mods menu without messing up the load order
- [Balatro-Mod-Updater](https://github.com/SilvertongueRED/Balatro-Mod-Updater) - keeps your mods, Steamodded and Lovely up to date, with backups and a rescue screen when an update breaks the game
- [Balatro-SaveRewinder-Config-Fix](https://github.com/SilvertongueRED/Balatro-SaveRewinder-Config-Fix) - Save Rewinder fork with a config fix: automatic save points and one key to rewind
- [Balatro-Preview-Accuracy-Update](https://github.com/SilvertongueRED/Balatro-Preview-Accuracy-Update) - previews the score and dollars you will get from the selected cards, accuracy update
- [BalatroMods-HoldForFinalHandScore-Update](https://github.com/SilvertongueRED/BalatroMods-HoldForFinalHandScore-Update) - holds the final hand score on screen long enough to read it
- [Main-Menu-Theme-Selector](https://github.com/SilvertongueRED/Main-Menu-Theme-Selector) - choose your main menu colours, background theme and title logo
- [Better Mouse and Gamepad (bmag)](https://github.com/SilvertongueRED/bmag) - bind any key or button to quick actions like multiselect, easier on your hands
- [Balatro-Music-Selector-Fixes-and-Features](https://github.com/SilvertongueRED/Balatro-Music-Selector-Fixes-and-Features) - pick extra soundtracks or your own music without installing all of Cardsauce
<!-- other-mods:end -->
