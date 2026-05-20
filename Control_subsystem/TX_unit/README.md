# TX_unit

The TX unit provides the capability to connect a JR-compatible control transmitter module to the remote unit hub for subsequent two-way data exchange with the control panel connected to the station control unit. The general view of the TX unit with the control transmitter installed is shown in the image.

<img width="600" alt="General view of the TX unit with the control transmitter installed" src="picture/general_view_of_the_TX_unit_with_the_transmitter_module_installed.png" />

## Brief Technical Parameters

| Parameter | Value | Note |
|----------|---------|---------|
| Control protocol | CRSF | Via S.Port |
| Transmission interface | Differential signal of the RS-485 standard | |
| Operating mode | Two-way | Control + telemetry |
| TX unit power supply | From the remote unit hub | Via XS2 |
| Control transmitter TX module power supply | 8V | From the TX unit |
| TX unit output voltage via XS3 connector | 8V | Maximum continuous current 2A |
| Cooling | Passive | Heatsinks + ventilation holes |
| Shielding | Partial | |

### Interfaces

| Connector | Purpose | Main signals | Note |
|--------|------------|----------------|----------|
| XS1 | Connection of the control transmitter | VCC, GND, CRSF (S.Port) | JR-compatible control transmitters are supported |
| XS2 | Connection to the remote unit hub | +BAT, GND, differential signal of the RS-485 standard | |
| XS3 | 8V power output | VCC, GND | Connection of high-power control transmitters |

## Circuitry and Functionality of the TX Unit for the Control Transmitter

The TX unit is powered from the remote unit hub. The voltage from the XS2 connector goes to the common ground bus (for which a copper cooling heatsink is used) and to the voltage converter, which generates 8V to power the interface converter and the control transmitter (make sure your TX module supports 8V power). The 8V voltage is additionally output to the XS3 connector to allow powering high-power control transmitters that require external power. Note that a high-power control transmitter, when powered from the XS3 connector, should not have electrical contact with the GND pin of the XS1 connector to prevent a ground loop.

Two-way data exchange between the control transmitter and the control panel is carried out using the RS-485 standard via the ground control station's switching lines. Control signals via the XS2 connector are fed to the interface converter (BARVINOK-5 RS-485 nano V2.1 module), which converts the differential signal of the RS-485 standard into a high-speed CRSF protocol signal and sends it to the control transmitter via the S.Port pin of the XS1 connector.

Stabilization of the device's temperature modes is provided by a passive cooling system consisting of ventilation holes in the housing, a silicone thermal pad, and a copper heatsink. The copper heatsink is used as the common ground (GND) bus, which allows it to perform the function of an additional shield to protect against electromagnetic interference.

<img width="800" alt="Schematic diagram of the TX unit for the control transmitter" src="schematic_diagram/schematic_diagram_of_the_TX_unit.JPG" />

## List of Necessary Components for Manufacturing One TX Unit

| Name | Quantity | Note |
| :--- | :--- | :---: |
| BARVINOK-5 RS-485 nano V2.1 interface converter module | 1 pc | Ukrainian-made module [purchase BARVINOK-5 RS-485 nano V2.1 from the manufacturer](https://prom.ua/ua/p2693881056-adapter-port-485.html) |
| GUTI ELECTRONICS BEC12S-PRO voltage converter | 1 pc | Ukrainian analog of Matek BEC 12S PRO [purchase GUTI ELECTRONICS BEC12S-PRO from the manufacturer](https://prom.ua/ua/p2814749849-otechestvennyj-analog-matek.html) |
| GX12-6 pin panel mount plug (male) | 1 pc | XS2 |
| DC-022 power socket | 1 pc | XS3 |
| Pin header 1x40 2.54mm pitch L=25mm | 3 pins | |
| Pin header 1x40 2.54mm pitch L=15mm | 3 pins | |
| Double-sided prototyping board with 2.54 mm pitch | 30 mm x 70 mm |  |
| Self-adhesive electrical insulating paper 0.2 mm | 30 mm x 30 mm |  |
| Sheet copper 0.8 mm thick | 26 mm x 57 mm |  |
| Silicone thermal pad 2 mm 6W/m.k | 26 mm x 57 mm |  |
| Copper wire 20 AWG with silicone insulation, red | 200 mm |  |
| Copper wire 20 AWG with silicone insulation, black | 250 mm |  |
| Copper wire 26 AWG with silicone insulation, red | 100 mm |  |
| Copper wire 26 AWG with silicone insulation, black | 50 mm |  |
| Copper wire 26 AWG with silicone insulation, green | 80 mm |  |
| Copper wire 26 AWG with silicone insulation, blue | 80 mm |  |
| Screw M3x8 DIN 965 | 2 pcs |  |
| Nut M3 DIN 934 | 2 pcs |  |
| Screw M2x10 DIN 7985 | 12 pcs |  |
| Washer M2 DIN 125 | 12 pcs |  |
| Nut M2 DIN 934 | 12 pcs |  |
| Part 1 - 3D print | 1 pc |  |
| Part 2 - 3D print | 1 pc |  |

## 3D Printing Settings and Material Used

| Parameter | Value |
| :---: | :---: |
| Number of perimeters | 4 |
| Solid top and bottom layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Supports | Tree-like |

Material: coPET black MonoFilament

## XS1 Connector Assembly Process

The XS1 connector is formed by mounting long and short pins on the adapter board, which is made from a double-sided prototyping board. Long pins (L=25mm) are soldered in such a way that they do not extend beyond the adapter board on the side of the short pins. A thin copper wire is used as jumpers between the mounting holes of the prototyping board.

<img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_1.jpg" /> <img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_2.jpg" />

Short pins (L=15mm) are soldered in the opposite direction relative to the long pins.

<img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_3.jpg" />

On the side of the short pins, three layers of self-adhesive electrical insulating paper are applied to the adapter board to protect against short circuits from the adapter board's contact pads to the common ground (GND) polygon of the interface converter.

<img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_4.jpg" />

The short pins are soldered to the interface converter, the excess length of the central (GND) and right (S.Port) pins is cut off, and the left (VCC) pin is trimmed by approximately half, thus forming the point to which 8V from the voltage converter will be supplied to power the interface converter and the control transmitter. The long pins are inserted into the corresponding holes of the unit's base during the installation of the interface converter.

<img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_5.jpg" /> <img width="400" alt="XS1 connector assembly process" src="picture/XS1_connector_assembly_process_6.jpg" />

## Hardware Fasteners Details

| Name | Type/Size | Quantity | Note |
| :--- | :--- | :---: | :---: |
| Screw | M3x8 DIN 965 | 2 pcs | Mounting the BARVINOK-5 RS-485 nano V2.1 module |
| Nut | M3 DIN 934 | 2 pcs | Mounting the BARVINOK-5 RS-485 nano V2.1 module |
| Screw | M2x10 DIN 7985 | 6 pcs | Mounting the heatsink |
| Washer | M2 DIN 125 | 6 pcs | Mounting the heatsink |
| Nut | M2 DIN 934 | 6 pcs | Mounting the heatsink |
| Screw | M2x10 DIN 7985 | 6 pcs | Mounting the cover |
| Washer | M2 DIN 125 | 6 pcs | Mounting the cover |
| Nut | M2 DIN 934 | 6 pcs | Mounting the cover |

## Wire Usage Details

| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 100 mm | GND bus (cooling heatsink) - XS2 |
| 20 AWG black | 50 mm | GND bus (cooling heatsink) - 12S PRO voltage converter |
| 26 AWG black | 50 mm | GND bus (cooling heatsink) - interface converter |
| 20 AWG black | 100 mm | GND bus (cooling heatsink) - XS3 |
| 26 AWG green | 80 mm | Interface converter - XS2 |
| 26 AWG blue | 80 mm | Interface converter - XS2 |
| 20 AWG red | 100 mm | 12S PRO voltage converter - XS2 |
| 20 AWG red | 100 mm | 12S PRO voltage converter - XS3 |
| 26 AWG red | 100 mm | Interface converter - XS3 |
