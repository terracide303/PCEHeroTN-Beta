# Just the Tang Nano (no Pico)

The Tang Nano 20K has its own small chip, the BL616. With this firmware it runs the
menu, the SD card and the USB pads. You need no Pico and no shield.

**Newer boards only** (marked 3923). On older boards it gets stuck; see *Going back*.

## Files

| File | What it is |
|---|---|
| `bl616_fpga_partner_nano20k_v3923.bin` | Keeps the BL616 loading cores, as before |
| `fpga_companion_nano20k_v3923_gamepad_setup.bin` | The menu, SD card and USB pads, with Setup Gamepad |
| `flash_nano20k_v3923.ini` | Tells the flash tool where each file goes |

## Install

You need `BLFlashCommand` from the
[bouffalo_sdk](https://github.com/bouffalolab/bouffalo_sdk/tree/master/tools/bflb_tools/bouffalo_flash_cube).

1. Unplug the Tang Nano.
2. Hold **UPDATE** (next to the HDMI port) and plug it back in. It shows up as
   `Bouffalo CDC DEMO`, with a serial port.
3. In this folder, run (with your own port instead of `COM8`):

   ```
   BLFlashCommand --interface=uart --baudrate=2000000 --port=COM8 --chipname=bl616 --cpu_id= --config=flash_nano20k_v3923.ini
   ```

4. Unplug and plug in again. It shows up as `SIPEED USB Debugger`, and loading cores
   works as before.
5. Load the core as in the main README.

## Use

Plug a USB-C OTG adapter into the Tang, then a USB hub, then the pads (and a keyboard
if you like). **S1** opens the menu.

If your pad does not work in the menu, run **Setup Gamepad** at the bottom of the menu.
That setup is lost when you power off, so run it again after each power-up. Saving it
comes in a later version. Pads that work without setup are not affected.

## Going back

Use the `encrypted` files in
[FPGA-Companion's friend_20k folder](https://github.com/MiSTle-Dev/FPGA-Companion/tree/main/src/bl616/friend_20k),
with the same UPDATE step.
