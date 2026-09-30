# PCEHeroTN — Beta (Release Candidate 1)

PC Engine / TurboGrafx-16 for the Tang Nano 20K.

<p align="center">
  <img src="images/raiden.jpg" width="49%" alt="Raiden title screen">
  <img src="images/salamander.jpg" width="49%" alt="Salamander title screen">
</p>
<p align="center"><i>Raiden and Salamander on a Tang Nano 20K, photographed from the TV.</i></p>

## What you need

- Tang Nano 20K
- A Raspberry Pi Pico (RP2040): on a MiSTeryShield20k, or wired to the Tang on a breadboard (see below)
- A micro SD card (FAT32)
- One or two USB gamepads, and a USB keyboard for the menu
- HDMI screen

### Breadboard instead of the shield

Wire the Pico to the Tang Nano like this:

| Tang Nano 20K pin | Signal | Pico pin |
|---|---|---|
| 42 | MISO | GP16 |
| 41 | MOSI | GP19 |
| 56 | CSN | GP17 |
| 54 | SCK | GP18 |
| 51 | IRQ | GP22 |
| 5V | power | VBUS |
| GND | ground | GND |

The gamepads plug into a USB-A socket on the Pico: D+ to GP2, D- to GP3,
VBUS to the Pico's VBUS and GND to GND. For a keyboard and two pads on one
socket, use a small USB hub. A picture of this setup is in the
[FPGA-Companion wiring guide](https://github.com/MiSTle-Dev/FPGA-Companion/tree/main/src/rp2040#example-wiring).

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

- A few games do not start yet, for example Street Fighter II.
- HuCards only. No CD-ROM games and no SuperGrafx.
- The Pico firmware has no WiFi or Bluetooth. Use wired USB pads.

## Gamepad does not work?

The folder [`gamepad-setup`](gamepad-setup) has a test version of the Pico
firmware that lets you set up your gamepad button by button from the F12 menu.
It is not part of the normal release: it adds entries to every core's menu and
uses PC Engine button names, which goes against the idea of one neutral
firmware for all cores. It is only for beta testers who do not have a working
controller. See [its README](gamepad-setup/README.md).

## Credits

This builds on the work of Torlus, the MiSTer and MiST teams, Till Harbaum, MiSTle-Dev and others.
See [CREDITS.md](CREDITS.md).
