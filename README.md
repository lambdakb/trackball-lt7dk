# LT7DK PMW3360 Trackball Development Kit

[![Documentation](https://img.shields.io/badge/Documentation-Latest-brightgreen?style=for-the-badge&logo=docusaurus&logoColor=white)](https://lambdakb.dev/devices/lt7dk)
[![GitHub Release](https://img.shields.io/github/v/release/lambdakb/trackball-lt7dk?label=Release&style=for-the-badge&logo=github&logoColor=white)](https://github.com/lambdakb/trackball-lt7dk/releases/latest)
[![License](https://img.shields.io/badge/License-CERN--OHL--S--2.0-0099B0?style=for-the-badge&logo=opensourcehardware&logoColor=white)](/LICENSE)
[![KiCad](https://img.shields.io/badge/KiCad-v8-orange?style=for-the-badge&logo=kicad&logoColor=white&logoSize=auto)](https://www.kicad.org/)

## PCB

|             Front             |            Back             |
| :---------------------------: | :-------------------------: |
| [![PCB Front]][PCB Front PNG] | [![PCB Back]][PCB Back PNG] |

[PCB Front]: output/img/lt7dk-pcb-top.svg
[PCB Front PNG]: output/img/lt7dk-pcb-top.png
[PCB Back]: output/img/lt7dk-pcb-bottom.svg
[PCB Back PNG]: output/img/lt7dk-pcb-bottom.png

The PCB has been designed in [KiCad EDA 8.0](https://www.kicad.org/) using the [`kicad-lkbd`](https://github.com/lambdakb/kicad-lkbd) libraries.

You can preview the project files using [KiCanvas](https://kicanvas.org/?github=https%3A%2F%2Fgithub.com%2Flambdakb%2Ftrackball-lt7dk%2Fblob%2Fmain%2Fpcb%2Flt7dk-pcb.kicad_pro) directly in your browser and download the latest fabrication files for JLCPCB from the [latest release](https://github.com/lambdakb/trackball-lt7dk/releases/latest/).

The exported schematic is also available under [`output/schematics`](output/schematics/).

## Firmware

Firmware has been built using the [`vial` fork](https://github.com/vial-kb/vial-qmk) of [QMK](https://qmk.fm).

## References

### Inspiration

- [aki27kbd trackball_module](https://github.com/aki27kbd/trackball_module)
- [Ploopy Nano Trackball](https://ploopy.co/nano-trackball/) ([source](https://github.com/ploopyco/nano-trackball))
- [Ploopy Adept Trackball](https://ploopy.co/adept-trackball/) ([source](https://github.com/ploopyco/adept-trackball))
- [jfedor2 DIY trackball with scroll ring](https://github.com/jfedor2/scroll-ring-trackball)
- [The Orb trackball](https://github.com/dpapavas/orb-trackball)
- [brickbots aball](https://github.com/brickbots/aball)

### PCB Designs

- [jfedor2 PMW3360 Breakout Board](https://github.com/jfedor2/pmw3360-breakout)
- [jfedor2 PMW3360+RP2040](https://github.com/jfedor2/rp2040-pmw3360)
- [asav.dev PMW3360 Module](https://asav.dev/pmw3360/)
- [SideraKB PMW3360 PCB](https://github.com/siderakb/pmw3360-pcb)
- [protieusz Omega-Petit](https://github.com/protieusz/Omega-Petit)

## License

This design is licensed under the [CERN Open Hardware Licence Version 2 – Strongly Reciprocal (CERN-OHL-S-2.0)](https://opensource.org/license/cern-ohl-s).

You are free to use, modify, and distribute this design for any purpose, provided that:

- **Attribution**: Appropriate credit is given, a link to the license is provided, and any modifications are clearly indicated.
- **Reciprocity**: Any derivative works must be released under the same license.

If you are a retailer or business interested in producing or selling this design or related products, I’d love to discuss it! Please feel free to reach out so we can explore potential arrangements.
