# PCEHeroTN — Beta (Release Candidate 1)

PC Engine / TurboGrafx-16 for the Tang Nano 20K.

## What you need

- Tang Nano 20K
- MiSTeryShield20k with the Pico (RP2040)
- A micro SD card (FAT32)
- One or two USB gamepads, and a USB keyboard for the menu
- HDMI screen

## Files

| File | What it is |
|---|---|
| `PCEHeroTN_RC1.fs` | The core, for the Tang Nano 20K |
| `fpga_companion_msp20k_nowifi.uf2` | Firmware for the Pico on the shield |

## Install

**1. The Pico firmware (once).**
Hold the BOOTSEL button on the Pico and plug it into your computer.
A drive called `RPI-RP2` appears. Copy `fpga_companion_msp20k_nowifi.uf2` onto it.
The Pico restarts by itself.

**2. The core.**
Plug the Tang Nano into your computer and run:

```
openFPGALoader -b tangnano20k -f PCEHeroTN_RC1.fs
```

This writes it to the board's flash, so it stays after you unplug.

**3. Games.**
Make a folder called `PCE` on the SD card and put your `.pce` files in it.
Put the card in the Tang Nano's SD slot.

## Play

Power up. The screen stays black until you pick a game.
Press **F12** on a USB keyboard to open the menu, go to the `PCE` folder and choose a game.

Two players: plug in a second USB pad.

## Known issues

- A few games do not start yet, for example Raiden (US) and Cadash (US).
- HuCards only. No CD-ROM games and no SuperGrafx.
- The Pico firmware has no WiFi or Bluetooth. Use wired USB pads.
