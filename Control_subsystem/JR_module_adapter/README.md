# JR_module_adapter

The JR_module_adapter provides the capability to connect a control panel with a JR-compatible bay to the station control unit for subsequent two-way data exchange with the control transmitter on the station's remote unit.

<img width="600" alt="General view of the JR module" src="picture/general_view_of_the_JR_module.png" />

## Brief Technical Parameters

| Parameter | Value | Note |
|----------|---------|---------|
| Control protocol | CRSF | Via S.Port |
| Transmission interface | Differential signal of the RS-485 standard | |
| Operating mode | Two-way | Control + telemetry |
| JR module adapter power supply | 5–8.4 V | From the control panel |
| Cooling | Passive | Heatsinks + ventilation holes |
| Shielding | Partial | |

### Interfaces

| Connector | Purpose | Main signals | Note |
|--------|------------|----------------|----------|
| XS1 | Connection to the control panel | +BAT, GND, CRSF | The control panel must be equipped with a JR-compatible bay |
| XS2 | Connection to the station control unit | Differential signal of the RS-485 standard, GND | |

## Circuitry and Functionality of the JR Module Adapter

The adapter is powered directly from the control panel via the XS1 connector in the 5V–8.4V range.

The high-speed signal from the control panel via the S.Port pin (CRSF protocol) of the XS1 connector is fed to the interface converter (BARVINOK-5 RS-485 nano V2.1 module), which converts it into a differential signal of the RS-485 standard and outputs it through the XS2 connector into the ground control station's switching lines.

Stabilization of the device's temperature modes is provided by a passive cooling system consisting of ventilation holes in the housing, a silicone thermal pad, and a copper heatsink. The heatsink is electrically connected to the common wire (GND), allowing it to perform the function of an additional shield to protect against electromagnetic interference.

<img width="800" alt="Schematic diagram of the JR module" src="schematic_diagram/schematic_diagram_of_the_JR_module_adapter.JPG" />

## List of Necessary Components for Manufacturing One JR Module Adapter

| Name | Quantity | Note |
| :--- | :--- | :---: |
| BARVINOK-5 RS-485 nano V2.1 interface converter module | 1 pc | Ukrainian-made module [purchase BARVINOK-5 RS-485 nano V2.1 from the manufacturer](https://prom.ua/ua/p2693881056-adapter-port-485.html) |
| PCE-C-05 connector | 1 pc | XS1 |
| GX12-6 pin panel mount plug (male) | 1 pc | XS2 |
| Double-sided prototyping board with 2.54 mm pitch | 30 mm x 70 mm |  |
| Sheet copper 0.8 mm thick | 25 mm x 28 mm |  |
| Silicone thermal pad 2 mm 6W/m.k | 25 mm x 28 mm |  |
| Copper wire 26 AWG with silicone insulation, black | 260 mm |  |
| Copper wire 26 AWG with silicone insulation, green | 170 mm |  |
| Copper wire 26 AWG with silicone insulation, blue | 170 mm |  |
| Screw M2x5 DIN 7985 | 2 pcs |  |
| Screw M2x6 DIN 965 | 3 pcs |  |
| Screw M2x10 DIN 7985 | 9 pcs |  |
| Washer M2 DIN 125 | 8 pcs |  |
| Nut M2 DIN 934 | 14 pcs |  |
| Screw M3x8 DIN 965 | 2 pcs |  |
| Nut M3 DIN 934 | 2 pcs |  |
| Part 1 - 3D print | 1 pc |  |
| Part 2 - 3D print | 1 pc |  |
| Part 3 - 3D print | 1 pc |  |
| Part 4 - 3D print | 1 pc |  |

## 3D Printing Settings and Material Used

| Parameter | Value |
| :---: | :---: |
| Number of perimeters | 4 |
| Solid top and bottom layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Supports | Tree-like |

Material: coPET black MonoFilament

## Hardware Fasteners Details

| Name | Type/Size | Quantity | Note |
| :--- | :--- | :---: | :---: |
| Screw | M2x5 DIN 7985 | 2 pcs | Mounting the board with the XS1 connector |
| Nut | M2 DIN 934 | 2 pcs | Mounting the board with the XS1 connector |
| Screw | M2x10 DIN 7985 | 1 pc | Mounting the XS1 connector retainer |
| Nut | M2 DIN 934 | 1 pc | Mounting the XS1 connector retainer |
| Screw | M3x8 DIN 965 | 2 pcs | Mounting the BARVINOK-5 RS-485 nano V2.1 module |
| Nut | M3 DIN 934 | 2 pcs | Mounting the BARVINOK-5 RS-485 nano V2.1 module |
| Screw | M2x5 DIN 7985 | 4 pcs | Mounting the heatsink |
| Washer | M2 DIN 125 | 4 pcs | Mounting the heatsink |
| Nut | M2 DIN 934 | 4 pcs | Mounting the heatsink |
| Screw | M2x6 DIN 965 | 3 pcs | Mounting the internal strip to the module base |
| Nut | M2 DIN 934 | 3 pcs | Mounting the internal strip to the module base |
| Screw | M2x10 DIN 7985 | 4 pcs | Mounting the module cover to its base |
| Washer | M2 DIN 125 | 4 pcs | Mounting the module cover to its base |
| Nut | M2 DIN 934 | 4 pcs | Mounting the module cover to its base |

## Wire Usage Details

| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 80 mm | XS1 - interface converter |
| 26 AWG green | 80 mm | XS1 - interface converter |
| 26 AWG blue | 80 mm | XS1 - interface converter |
| 26 AWG black | 90 mm | Interface converter - XS2 |
| 26 AWG green | 90 mm | Interface converter - XS2 |
| 26 AWG blue | 90 mm | Interface converter - XS2 |
| 26 AWG black | 90 mm | XS2 - heatsink |
