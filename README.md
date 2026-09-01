# AirGradient SUNX CO₂ Sensor Module — Hardware

> KiCad hardware design files for the AirGradient SUNX CO₂ sensor module — a plug-in adapter board that carries a SenseAir Sunrise/Sunlight ("SUNX") NDIR CO₂ sensor in AirGradient air quality monitors, including the [Open Air Max](https://www.airgradient.com/professional/products/open-air-max/).

## Overview

A 2-layer adapter for the SenseAir Sunrise/Sunlight family: two sockets matching the sensor's 5-pin and 4-pin headers, an HT7333 3.3 V LDO with bulk decoupling for the sensor supply, and a solder jumper (JP1) for sensor power selection. Power and UART are routed to an 8-pin host connector.

This is the SUNX-only variant of AirGradient's CO₂ sensor adapter family — v2.0 of the original combined design with S8 support removed; the [S8-only board](https://github.com/Open-Air-Foundation/pcb-module-s8) and the [combined S8 + SUNX board](https://github.com/Open-Air-Foundation/pcb-module-s8-sunx) live in their own repositories.

## Design structure

A single KiCad project in `sunx/`: one schematic sheet and a 2-layer board.

## Repository structure

```
sunx/                        # KiCad project (schematic + board), production/
```

## Key components

| Function | Part | Ref |
|---|---|---|
| Sensor sockets (5-pin + 4-pin) | Pin sockets, 2.54 mm | J1, J2 |
| 3.3 V LDO (sensor supply) | HT7333-3 (SOT-89) | U1 |
| Bulk decoupling | 2× 10 µF, 2× 22 µF | C1–C4 |
| Sensor power select (3-way solder jumper) | — | JP1 |
| Host connector (8-pin) | Molex | con1 |

## Toolchain

- **KiCad 9** (file format 2025-01). All symbols, footprints, and 3D models come from the KiCad standard libraries — the project opens without any extra library setup.

## Fabrication

`sunx/production/` holds the released set: Gerber zip (`sunx-v2.0.zip`; the Gerber filenames inside keep the design's original `CO2-sensor-pcb` naming), BOM, and pick-and-place positions.

## Versioning & releases

Hardware revisions are tagged on this repository. Per-version release notes and the matching production file set are published on the [GitHub Releases](../../releases) page.

> The `v2.1` branch carries work in progress (AP2112K-3.3 LDO, 0 Ω power-select links replacing the solder jumper, revised silkscreen and placement). It is untested and unreleased — do not order from it.

## License

This is open-source hardware. The design files in this repository are licensed under the
[Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/) license — see [LICENSE](LICENSE).

You are free to use, modify, and manufacture these designs, including commercially, provided you credit AirGradient and share derivative designs under the same license.

## Maintainers

AirGradient hardware team.
