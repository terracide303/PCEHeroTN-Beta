# What changed from RC1 to RC3

RC2 was paused because of graphics glitches in some games. RC3 fixes them and brings
everything RC2 had, plus a few new things. **RC3 needs a Pico** (see Known issues).

## New

- **Faster:** less slowdown in busy scenes, for example R-Type II.
- **Colours:** menu → Colours: Original or Raw RGB. Original is the MiSTer colour table
  (the default). Raw RGB is a bit brighter, the RC1 look.
- **Scanlines:** menu → Scanlines: Off / CRT-Lite. Looks like an old CRT TV.
- **S1 opens the menu**, like F12.
- **Turbo:** menu → Controller: 2 Turbo. Pad buttons 3 and 4 are turbo I and II,
  L and R are faster turbo. Both pads.
- **Reset** in the menu restarts the game.
- **No game**, then Reset, goes back to the colour bars.
- **Overscan:** Hidden or Visible, as on MiSTer. Hidden is the default and shows thin
  black strips top and bottom.
- **Border:** Original or Black. (Not yet checked on a game with a coloured border.)
- **Colour bars** when no game is loaded, instead of a black screen.

## Fixed

- The graphics glitches and crashes from RC2 (for example in Darius and Mr Heli).
- US HuCard dumps with reversed bits now boot as they are, for example Cadash (U).
- More reliable reads from the game memory and from the USB pads.
- Games that change screen width halfway down the picture. (Not yet checked on a game.)

## Not in RC3

- Running on just the Tang Nano (the BL616 chip, no Pico). It was in RC2, but we have not
  tested it with RC3. Please use a Pico for now.
