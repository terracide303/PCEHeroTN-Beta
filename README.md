# PCEHeroTN — Beta (Release Candidate 1)

PC Engine / TurboGrafx-16 for the Tang Nano 20K.

> **RC2 is paused.** We found a bug (graphics glitches in some games) and want to fix it
> first. Until then, please use RC1. RC2 comes back with the fix, including running on
> just the Tang Nano without a Pico. What it will bring: [CHANGES.md](CHANGES.md).

<p align="center">
  <img src="images/raiden.jpg" width="49%" alt="Raiden title screen">
  <img src="images/salamander.jpg" width="49%" alt="Salamander title screen">
</p>
<p align="center"><i>Raiden and Salamander on a Tang Nano 20K, photographed from the TV.</i></p>

## What you need

- Tang Nano 20K
- A Raspberry Pi Pico (RP2040): on a MiSTeryShield20k, or wired to the Tang on a breadboard
  as shown in the [FPGA-Companion wiring guide](https://github.com/MiSTle-Dev/FPGA-Companion/tree/main/src/rp2040#example-wiring)
- A micro SD card (FAT32)
- One or two USB gamepads, and a USB keyboard for the menu
- HDMI screen

## Files

| File | What it is |
|---|---|
| `PCEHeroTN_RC1.fs` | The core, for the Tang Nano 20K |
| `fpga_companion_msp20k_gamepad_setup.uf2` | Firmware for the Pico |

## Install

**1. The Pico firmware (once).**
Hold the BOOTSEL button on the Pico and plug it into your computer.
A drive called `RPI-RP2` appears. Copy `fpga_companion_msp20k_gamepad_setup.uf2` onto it.
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

- A few games do not start yet, for example Street Fighter II.
- HuCards only. No CD-ROM games and no SuperGrafx.

## Gamepad does not work?

The Pico firmware in this repo is **our own custom build** with an extra
**Setup Gamepad** menu. This breaks the idea of one neutral firmware for all cores (it
adds PC Engine button names to every core's menu), so it is **meant for beta testing only**.

Use **Setup Gamepad** at the bottom of the menu, and press each button it asks for.
ESC on the keyboard skips one. The PC Engine only needs the first 8.
**Remove Gamepad Setup** puts a pad back to normal. The setup is kept after power-off.

## Credits

This builds on the work of Torlus, the MiSTer and MiST teams, Alastair M. Robinson, Till Harbaum, MiSTle-Dev and others.
See [CREDITS.md](CREDITS.md).
