# Credits

PCEHeroTN is built on the work of many people. Thank you all.

## The PC Engine core

- **Gregory Estrade (Torlus)**: [FPGAPCE](https://github.com/Torlus/FPGAPCE), the original PC Engine in an FPGA that all of this comes from.
- **The MiSTer TurboGrafx16 core** ([MiSTer-devel/TurboGrafx16_MiSTer](https://github.com/MiSTer-devel/TurboGrafx16_MiSTer)): Sorgelig (MiSTer port), srg320 (the rewritten HuC6280 CPU and more), greyrogue, Kitrinx and dshadoff. We use its CPU, sound chip and clock logic.
- **The MiST TurboGrafx16 core** ([mist-devel/TurboGrafx16_FPGA](https://github.com/mist-devel/TurboGrafx16_FPGA)): the MiST developers. We use its video chips (VDC and VCE) and the top level.
- **Alastair M. Robinson ([robinsonb5](https://github.com/robinsonb5))**: his PC Engine SDRAM controller for MiST and his write-ups on [retroramblings.net](https://retroramblings.net/?p=1635) showed us how to feed the PC Engine fast enough from SDRAM on this kind of board.

## Borrowed parts

- **SDRAM controller**: Till Harbaum and Mateusz Nalewajski, from [NanoMig](https://github.com/MiSTle-Dev/NanoMig). GPL v3.
- **On-screen menu, SD card and USB input link**: Till Harbaum and the [MiSTle-Dev](https://github.com/MiSTle-Dev) project: [FPGA-Companion](https://github.com/MiSTle-Dev/FPGA-Companion) (Apache 2.0) and the menu display from [MiSTeryNano](https://github.com/MiSTle-Dev/MiSTeryNano) (GPL v3).
- **SD card reader**: WangXuan95, [FPGA-SDcard-Reader](https://github.com/WangXuan95/FPGA-SDcard-Reader) (GPL v3), with writing added by lfantoniosi in [WonderTANG](https://github.com/lfantoniosi/WonderTANG) (BSD 2-Clause).
- **HDMI video and sound**: Sameer Puri, [hdl-util/hdmi](https://github.com/hdl-util/hdmi). MIT / Apache 2.0.

## Pico firmware

`fpga_companion_msp20k_gamepad_setup.uf2` is [FPGA-Companion](https://github.com/MiSTle-Dev/FPGA-Companion) by Till Harbaum and MiSTle-Dev, built for the RP2040 with the gamepad setup added. From the [dev branch](https://github.com/terracide303/FPGA-Companion/tree/dev) of our fork. Apache 2.0.

## Colours

The Original colour table is the MiSTer TurboGrafx16 core's `palette.mif`.

## Scanlines

The CRT-Lite scanline effect is our own (PCEHeroTN / CRTLiteTN), modelled on how a CRT beam spreads.

## Hardware

- **Sipeed** for the Tang Nano 20K.
- The makers of the **MiSTeryShield20k**.

## Licences

The full licence texts are in the `licenses` folder.
