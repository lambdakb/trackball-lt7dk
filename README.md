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

### PCB Order

| Parameters                       | Value                  |
| -------------------------------- | ---------------------- |
| Base Material                    | FR4                    |
| Layers                           | 2                      |
| Dimensions                       | 62 × 84 mm             |
| PCB Thickness                    | 1.6 mm                 |
| PCB Color [^pcb-color]           | Black                  |
| Silkscreen                       | White                  |
| Surface Finish [^surface-finish] | Lead Free HASL or ENIG |
| Copper Weight                    | 1 oz                   |
| Via Covering                     | Tented                 |
| Min Via Hole Size                | 0.3 mm                 |
| Board Outline Tolerance          | ± 0.2 mm               |

[^pcb-color]: You can select any PCB color you want but some manufacturers such as JLCPCB may charge you more for uncommon combos (such as Blue PCB + ENIG Surface Finish).
[^surface-finish]: The "HASL (with lead)" option is extremely discouraged due to the risk of lead poisoning. We strongly recommend paying the premium for the "Lead Free HASL" option.

### JLCPCB Specific Options

<!-- NOTE: This is generic and used for ALL LambdaKB PCBs EXCEPT for cases PCB   -->

#### Mark on PCB

The following JCLPCB specific options are used to serialize PCBs on order. An 8 × 8 mm silkscreen square was added to the PCB to allow for a 2D barcode to be added.

| Parameters            | Value                       |
| --------------------- | --------------------------- |
| Mark on PCB           | 2D barcode (Serial Number)  |
| - Printing            | 2D barcode & Number         |
| - Code Type           | Data Matrix Code            |
| - Prefix              | `LKBD_LT7DK_v100`           |
| - Unique Number       | Remove                      |
| - Incrementing Number | _`YYMM01`_ (e.g.: `250300`) |
| - 2D Barcode Size     | 8 × 8 mm                    |
| - 2D Barcode Position | Specify Position            |

Serial numbers are based on the current date using the `YYMM01` format for its incrementing numbers. Orders in February 2025 would start then start it at `250300`, making the final serial `LKBD_LT7DK_v100_250300`.

## BOM

| Part                          | Ref.                                                          | Quantity | Optional | Remarks                                                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------- | :------: | :------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| PCB                           | [LT7DK PCB](./README.md#pcb)                                  |    1     |    ❌    | See [PCB](./README.md#pcb) section on how to order it.                                                                                                           |
| Pro Micro Controller          | [Arduino Pro Micro 5V], [Adafruit KB2040] or [nice!nano]      |    1     |    ❌    | Supports various Pro Micro style controller (including RP2040 based ones) as well as the nice!nano for wireless builds. [^wireless]                              |
| MCU Socket                    | [DIP-24 Round Socket (Wide, 15.24 mm)]                        |    1     |    ✅    | Recommended to socket the controller, can be omitted if soldered directly. Compatibles pins are required such as dismantled [LED strip male adapters].           |
| Reset Push Button             | [DIP 2pin Momentary Push Button (6 × 3.5 mm)]                 |    1     |    ✅    | Used as a reset switch, can be omitted if you flash the controller before installing it or if the controller can be put in bootloader mode from any other means. |
| Micro Switches                | [D2FC-F-7N Micro Switch] or compatible                        |   4-7    |    ❌    | Micro switches for mouse buttons, you do not have to populate all of them depending on how you intend to use the PCB.                                            |
| PMW3360 Optical Sensor & Lens | [PMW3360DM-T2QU + LM19-LSI]                                   |    1     |    ❌    | Optical mouse sensor and lens used to detect trackball movement.                                                                                                 |
| 1.8V DO                       | [TPS76318 Fixed 1.8V LDO (SOT-23-5)]                          |    1     |    ❌    | Power regulator for optical sensor.                                                                                                                              |
| 1uF Capacitor                 | [0805 SMD Ceramic Capacitor]                                  |    1     |    ❌    | Required by the optical sensor LDO.                                                                                                                              |
| 4.7uF Capacitors              | [0805 SMD Ceramic Capacitor]                                  |    2     |    ❌    | Power filtering capacitor for optical sensor and required LDO.                                                                                                   |
| 100nF Capacitors              | [0805 SMD Ceramic Capacitor]                                  |   1-2    |    ❌    | One if required for the power filtering of the optical sensor, the second one is only required if installing the NeoPixel RGB LED.                               |
| 10K Ω Resistor                | [0805 SMD Resistor]                                           |    1     |    ❌    | Required by the optical sensor.                                                                                                                                  |
| 39 Ω Resistor                 | [0805 SMD Resistor]                                           |    1     |    ❌    | Required by the optical sensor.                                                                                                                                  |
| 0.91" OLED Display            | [SSD1306 0.91" 128X32 OLED I²C Display Module]                |   0-1    |    ✅    | Optional, not recommended for wireless builds. [^wireless]                                                                                                       |
| NeoPixel RGB LED              | [WS2812B 5050 SMD RGB LED] or [SK6812 5050 SMD RGBW LED]      |   0-1    |    ✅    | Optional, MUST NOT be placed on wireless builds as 5V output is not provided on the RAW pin by the controller. [^wireless]                                       |
| Power Slide Switch            | [PCM12SMTR] or [MSK-12C02]                                    |    1     |    ✅    | Only required for battery powered wireless builds. [^wireless]                                                                                                   |
| Battery Connector             | [JST-PH 2pin right-angle Male Connector]                      |    1     |    ✅    | Only needed for battery powered wireless builds if the battery is not soldered directly to the board (recommended). [^wireless]                                  |
| 3.7V Li-Po Battery            | [603449 (1100 mAh)] or [503450 (1000 mAh)] 3.7V Li-Po Battery |    1     |    ✅    | Only required for battery powered wireless builds, any 3.7 V (1 Cell) Li-Po battery slimmer than 8 mm with a JST-PH connector should work. [^wireless]           |

[Arduino Pro Micro 5V]: https://www.sparkfun.com/pro-micro-5v-16mhz.html
[Adafruit KB2040]: https://www.adafruit.com/product/5302
[nice!nano]: https://nicekeyboards.com/nice-nano/
[DIP-24 Round Socket (Wide, 15.24 mm)]: https://www.aliexpress.com/item/1005005770166098.html
[LED strip male adapters]: (https://www.aliexpress.com/item/1005005742644313.html)
[DIP 2pin Momentary Push Button (6 × 3.5 mm)]: https://www.aliexpress.com/item/1005001849576755.html
[D2FC-F-7N Micro Switch]: https://www.aliexpress.com/item/1005005018374123.html
[PMW3360DM-T2QU + LM19-LSI]: https://www.aliexpress.com/item/4000904265601.html?
[TPS76318 Fixed 1.8V LDO (SOT-23-5)]: https://www.aliexpress.com/item/1005007852956393.html
[0805 SMD Ceramic Capacitor]: https://www.aliexpress.com/item/32812155708.html
[0805 SMD Resistor]: https://www.aliexpress.com/item/32847143167.html
[WS2812B 5050 SMD RGB LED]: https://www.aliexpress.com/item/4001345875756.html
[SK6812 5050 SMD RGBW LED]: https://www.aliexpress.com/item/32666691387.html
[SSD1306 0.91" 128X32 OLED I²C Display Module]: https://www.aliexpress.com/item/32777216785.html
[PCM12SMTR]: https://www.digikey.com/en/products/detail/c-k/PCM12SMTR/1640112
[MSK-12C02]: https://www.aliexpress.com/item/4000685483225.html
[JST-PH 2pin right-angle Male Connector]: https://www.aliexpress.com/item/1005004955655144.html
[603449 (1100 mAh)]: https://amzn.eu/d/e3uVbqB
[503450 (1000 mAh)]: https://aliexpress.com/item/1005003198563309.html

[^wireless]: See [Wireless Support](./README.md#wireless-support) for more details.

## Firmware

Firmware has been built using the [`vial` fork](https://github.com/vial-kb/vial-qmk) of [QMK](https://qmk.fm).

## Wireless Support

To add wireless support to this keyboard, you will need a controller that provides power input and a charging circuit between the top RAW and GND such as the `nice!nano`.

The PCB itself provides a way to attach a JST-PH connector as well as a slide switch for power management. This slide switch must be set to ON for the charging circuit to work.

This hasn't been extensively tested yet and should be considered experimental (no wireless firmware will be provided for now). The feature was added to the PCB as way for us to prototype a potential wireless keyboard.

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
