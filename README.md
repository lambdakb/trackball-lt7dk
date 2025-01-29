# LT7DK PMW3360 Trackball Development Kit

[![Documentation](https://img.shields.io/badge/Documentation-Latest-brightgreen?style=for-the-badge&logo=docusaurus&logoColor=white)](https://lambdakb.dev/devices/lt7dk)
[![GitHub Release](https://img.shields.io/github/v/release/lambdakb/trackball-lt7dk?label=Release&style=for-the-badge&logo=github&logoColor=white)](https://github.com/lambdakb/trackball-lt7dk/releases/latest)
[![License](https://img.shields.io/badge/License-CERN--OHL--S--2.0-0099B0?style=for-the-badge&logo=opensourcehardware&logoColor=white)](/LICENSE)
[![KiCad](https://img.shields.io/badge/KiCad-v8-orange?style=for-the-badge&logo=kicad&logoColor=white&logoSize=auto)](https://www.kicad.org/)

## PCB

|    Front     |    Back     |
| :----------: | :---------: |
| ![PCB Front] | ![PCB Back] |

[PCB Front]: output/img/lt7dk-pcb-top.svg
[PCB Back]: output/img/lt7dk-pcb-bottom.svg

The PCB has been designed in [KiCad EDA 8.0](https://www.kicad.org/) using the [`kicad-lkbd`](https://github.com/lambdakb/kicad-lkbd) libraries and [`kbplacer`](https://github.com/adamws/kicad-kbplacer).

You can preview the project files using [KiCanvas](https://kicanvas.org/?github=https%3A%2F%2Fgithub.com%2Flambdakb%2Ftrackball-lt7dk%2Fblob%2Fmain%2Fpcb%2Flk23m-pcb.kicad_pro) directly in your browser and download the latest fabrication files for JLCPCB from the [latest release](https://github.com/lambdakb/keyboard-lk23m/releases/latest/).

The exported schematic is also available under [`output/schematics`](output/schematics/).

## Firmware

Firmware has been built using the [`vial` fork](https://github.com/vial-kb/vial-qmk) of [QMK](https://qmk.fm).

## License

This design is licensed under the [CERN Open Hardware Licence Version 2 – Strongly Reciprocal (CERN-OHL-S-2.0)](https://opensource.org/license/cern-ohl-s).

You are free to use, share, and modify the design for any purpose, provided that:

- **Attribution**: Appropriate credit is given, a link to the license is provided, and any changes are indicated.
- **Reciprocity**: Any contributions or modifications must be distributed under the same license.

If you are a retailer or business interested in selling this design or related products, I’d love to discuss it! Please feel free to reach out so we can explore potential arrangements.

## References

### Inspiration

- [aki27kbd trackball_module](https://github.com/aki27kbd/trackball_module)
- [Ploopy Nano Trackball](https://ploopy.co/nano-trackball/) ([source](https://github.com/ploopyco/nano-trackball), PCB design can be viewed using [Altium 365 Viewer](https://www.altium365.com/viewer/))
- [Ploopy Adept Trackball](https://ploopy.co/adept-trackball/) ([source](https://github.com/ploopyco/adept-trackball), PCB design can be viewed using [Altium 365 Viewer](https://www.altium365.com/viewer/))
- [DIY trackball with scroll ring](https://github.com/jfedor2/scroll-ring-trackball)
- [DIY two-ball trackball](https://github.com/jfedor2/two-ball-trackball)
- [The Orb trackball](https://github.com/dpapavas/orb-trackball)
- [brickbots aball](https://github.com/brickbots/aball)

### PCB Designs

- [jfedor2 PMW3360 Breakout Board](https://github.com/jfedor2/pmw3360-breakout)
- [jfedor2 PMW3360+RP2040](https://github.com/jfedor2/rp2040-pmw3360)
- [asav.dev PMW3360 Module](https://asav.dev/pmw3360/)
- [Bastardkb PMW3360-PCB](https://github.com/Bastardkb/PMW3360-pcb)
- [Bastardkb Chabrydris PMW3360 Sensor PCB](https://github.com/Bastardkb/charybdis-pmw-3360-sensor-pcb)
- [SideraKB PMW3360 PCB](https://github.com/siderakb/pmw3360-pcb)
- [protieusz OmegaSupreme](https://github.com/protieusz/OmegaSupreme)
- [protieusz Omega-Petit](https://github.com/protieusz/Omega-Petit)
- [Ariamelon Kiwano](https://github.com/Ariamelon/Kiwano)

### Documentation

- [PMW3360 sensor datasheet](https://d3s5r33r268y59.cloudfront.net/datasheets/9604/2017-05-07-18-19-11/PMS0058-PMW3360DM-T2QU-DS-R1.50-26092016._20161202173741.pdf)
- [D2FC-F-7N microswitch specs & datasheet](https://www.mouser.fr/ProductDetail/Omron-Electronics/D2FC-F-7N100M?qs=iLKYxzqNS757BGMJVD2IKg%3D%3D)
- [Trackball bearing comparison](https://kbd.news/Trackball-bearing-comparison-1757.html)
