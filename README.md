# Adjustable Buck Converter
A small project to practice Altium Designer. I designed a 2-layer adjustable step-down converter, starting with requirements and calculations and finishing with the schematic and PCB layout.

The output is adjustable from 3.3V to 25V by a potentiometer in the feedback divider. The 7-30V input has ideal-diode reverse-polarity protection and an EMI filter.

![3D view](images/PCB_3D.png)

Full schematic and layout: [Buck_Converter_Schematic_and_Layout.pdf](Buck_Converter_Schematic_and_Layout.pdf)

## Specifications

| Parameter | Value |
|---|---|
| Input voltage | 7-30V |
| Output voltage | 3.3V to 25V, adjustable |
| Output current | up to 3A |
| PCB | 2 layers |

## Hardware Design

**Input stage.** A 5A slow-blow fuse feeds an ideal-diode circuit built from an LM74700-Q1 controller and an N-channel MOSFET (PSMN013-60YLX), which blocks reverse polarity with a lower drop than a series diode. An SMBJ33A TVS diode clamps input transients.

**Input EMI filter.** A common-mode choke (Würth 744273501) blocks common-mode noise, and a π filter with a 3.3µH inductor reduces the differential-mode noise from the converter's pulsed input current.

**Converter.** A TPS54560B step-down regulator with an external Schottky catch diode (SBR8U60P5), a 10µH output inductor, and polymer and ceramic output capacitors. A potentiometer in the feedback divider sets the output voltage.

## PCB Layout

![PCB layout](images/PCB_Layout.png)

## Schematic

![Schematic](images/Schematic.png)

## Repository contents

| Path | Contents |
|---|---|
| `Buck_Converter_Schematic_and_Layout.pdf` | Schematic and PCB layout, readable without Altium |
| `images/` | 3D view, layout and schematic images |

## Tools

Altium Designer

## License

Copyright © 2026 Michael Kochubey. All rights reserved.
This design is shared for viewing only. Reproduction, manufacturing or redistribution requires written permission.
