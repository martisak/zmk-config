# Sköldpad ZMK config

[![Build](https://github.com/martisak/zmk-config/actions/workflows/build.yml/badge.svg)](https://github.com/martisak/zmk-config/actions/workflows/build.yml)

[ZMK firmware](https://zmk.dev/) for the Sköldpad split keyboard
(`nice_nano_v2`), tuned for Swedish input and coding symbols.

## Layout

The keymap (`config/skoldpad.keymap`) assumes the **macOS Swedish** OS
keyboard layout.

- **Base layer** — `å ä ö` are produced by the right-pinky `[ ; '`
  positions, as on a normal Swedish keyboard.
- **NUM layer** (hold left thumb / toggle) — numbers and coding symbols.
  Symbols are emitted as the `Option`/`Shift` combos macOS Swedish uses
  (e.g. `@` = `Option+2`, `{` = `Shift+Option+8`); see the `SWE_*`
  defines at the top of the keymap.
- **FUNC layer** (`&mo 2`) — function keys, Bluetooth, output selection,
  screenshots.
- **Directional layer** (`&mo 3`) — arrow cluster.

## Building

Builds run in GitHub Actions on every push — see the badge above.
Download the `.uf2` artifacts from the latest successful run.

## Flashing

1. Plug in one half via USB.
2. Double-tap the reset button to enter the bootloader.
3. Copy the matching `.uf2` onto the `NICENANO` drive that appears.
4. Repeat for the other half.

On machines where the bootloader mass-storage volume is blocked, the
board also exposes a USB serial port, allowing serial DFU flashing via
[`adafruit-nrfutil`](https://github.com/adafruit/Adafruit_nRF52_nrfutil).
