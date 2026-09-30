# Gamepad setup (test firmware)

Use this only if your USB gamepad does not work, or its buttons are mixed up,
with the normal Pico firmware.

It is the same Pico firmware as the main one, with two extra entries at the
bottom of the F12 menu:

- **Setup Gamepad**: let go of all buttons and wait a moment. Then press each
  button it asks for. ESC on the keyboard skips one. It asks for 12 buttons;
  the PC Engine only uses the first 8 (UP, DOWN, LEFT, RIGHT, I, II, SELECT,
  RUN), so you can skip the last four with ESC.
- **Remove Gamepad Setup**: press a button on the pad and its setup is
  deleted. The pad goes back to working the normal way.

The setup is saved in the Pico itself, per gamepad model (up to 4 models). It
stays after you power off.

## Install

Hold the BOOTSEL button on the Pico and plug it into your computer. Copy
`fpga_companion_dev_gamepad_setup.uf2` onto the `RPI-RP2` drive.

To go back, do the same with `fpga_companion_msp20k_nowifi.uf2` from the
main folder.

## Why it is separate

The Pico firmware is meant to work the same for every core. This version
adds the two menu entries to every core's menu and uses PC Engine button
names, so it is no longer neutral. It is here for beta testers who do not
have a working controller, not as the final solution.

Please tell us which gamepad you used and whether it worked.
