# What changed from RC1 to RC2

## New

- **Runs on just the Tang Nano.** No Pico, no shield, no keyboard needed. The board's own
  BL616 chip runs the menu. See [bl616](bl616/README.md).
- **S1 opens the menu**, like F12.
- **Scanlines:** menu → Scanlines: Off / CRT-Lite. Looks like an old CRT TV.
- **Turbo:** menu → Controller: 2 Turbo. Pad buttons 3 and 4 are turbo I and II,
  L and R are faster turbo. Both pads.
- **Reset** in the menu restarts the game.
- **No game**, then Reset, goes back to the colour bars.
- **Overscan:** Hidden or Visible, as on MiSTer. Hidden is the default and shows thin
  black strips top and bottom.
- **Border:** Original or Black. (Not yet checked on a game with a coloured border.)
- **Colour bars** when no game is loaded, instead of a black screen.

## Fixed

- US HuCard dumps with reversed bits now boot as they are, for example Cadash (U).
- More reliable reads from the game memory.
- Games that change screen width halfway down the picture. (Not yet checked on a game.)
