# Remote unit hub

The remote unit hub provides power distribution, signal concentration, and switching of remote unit peripheral devices.

<img width="800" alt="General view of the remote unit hub" src="picture/general_view_concentrator_of_the_remote_unit.png" />

## Brief Technical Specifications of the Remote Unit Hub

| Parameter | Value | Note |
| :--- | :--- | :---: |
| Input voltage | 6S Li-ion/LiPo battery (Min. 22.2 V, Max. 25.2 V) | Power supply via connector XS1 from the station control unit |
| Power bus | +BAT | Direct from the station control unit battery |
| Auxiliary bus | +5 V | Formed by a DC-DC converter |
| Number of video inputs | 2 | XS3, XS4 |
| Input video signal type | Analog composite (CVBS) | Analog composite signal |
| Output video signal type | Analog differential | Signal conversion and amplification by module VA-Do-2/2 followed by transmission over twisted pair |
| Video input selection | Remote | Switching from the station control unit side |
| VRX control | Supported | Via ELRS Backpack (video inputs XS3 or XS4) or wired connection (XS3 only) |
| TX interface | Digital (differential) | XS2 data transmission via twisted pair |
| Power protection | TVS diode | Protection against inductive surges and overvoltage |
| Cooling | Passive | Copper heatsinks + ventilation holes |
| Shielding | Yes | Copper shields |

### Interfaces

| Connector | Application | Main Signals | Note |
| :--- | :--- | :---: | :---: |
| XS1 (GX20-8) | Connection to the control unit | +BAT, GND, differential lines | Power and signal exchange |
| XS2 (GX12-6) | TX unit connection | +BAT, GND, differential line | |
| XS3 (GX12-6) | Video input 1, VRX1 connection | +BAT, GND, CVBS, differential line | First video input, supports control via twisted pair |
| XS4 (GX12-6) | Video input 2, VRX2 connection | +BAT, GND, CVBS | Auxiliary video input |

## Schematic Design and Functionality of the Remote Unit Hub

<img width="800" alt="Schematic diagram of the remote unit hub" src="schematic_diagram/schematic_diagram_concentrator_of_the_remote_unit.JPG" />

The remote unit hub is powered through the XS1 connector, which receives voltage from the station control unit powered by a 6S3P Li-ion/LiPo battery pack. From the XS1 connector, power is supplied to the GND bus and the +BAT bus, from where it branches to the XS2, XS3, and XS4 connectors to power the peripheral devices and the voltage converter, which generates the +5V bus voltage powering the video amplifier. To protect the peripheral devices of the remote unit from transient processes in the line connecting it to the station control unit (caused by its inductive component), a semiconductor transient voltage suppressor (TVS) of type 1.5KE33A is used.

The TX unit is connected to the XS2 connector, and information exchange between it and the station control unit is performed via a twisted pair.

VRX units or other video signal sources are connected to the XS3 and XS4 connectors. The composite video signal from the XS3 and XS4 connectors goes to the video amplifier, which converts the composite signal to differential and transmits it via a twisted pair to the station control unit. There, after reverse conversion, it is distributed to the peripheral video devices of the station control unit. Selection of the active video input (XS3 or XS4) is done from the station control unit side. Video input XS3 has the option of additional information exchange with the station control unit via twisted pair for remote control of the video receiver.

Temperature stability of the video amplifier and voltage converter is ensured by copper cooling heatsinks and ventilation holes in the housing of the remote unit hub. The copper heatsinks are connected to the common ground (GND) bus, and together with the side shield of the hub board and the shield on the hub cover (which are also connected to the GND bus) minimize parasitic noise/interference on the video amplifier.

The remote unit hub has a rather high component density and involves working with different voltage levels. Successful assembly of the device requires schematic reading skills and intermediate experience in electronics assembly work.

<img width="600" alt="Assembly process of the remote unit hub" src="picture/installation_view.jpg" />

## Bill of Materials for One Remote Unit Hub

| Part Name | Qty | Note |
| :--- | :--- | :---: |
| VideoLink VA-Do-2/2 Video Amplifier | 1 pc | Ukrainian-made module [purchase VideoLink VA-Do-2/2 from the manufacturer](https://sezam.video/shop/videopidsilyuvach-z-simetrichnim-vihodom-aktivniy-balun-videolink-va-do-22/) |
| GUTI ELECTRONICS mBEC12S Voltage Converter | 1 pc | Ukrainian analog of Matek BEC 12S [purchase GUTI ELECTRONICS mBEC12S from the manufacturer](https://prom.ua/ua/p2814749850-otechestvennyj-analog-matek.html) |
| Panel mount plug GX20-8 pin (male) | 1 pc | XS1 |
| Panel mount plug GX12-6 pin (male) | 3 pcs | XS2-XS4 |
| Single-sided copper clad laminate 1.5 mm | 34 mm x 16 mm | Power bus board |
| TVS Diode 1.5KE33A DO201AD | 1 pc | |
| Self-adhesive copper tape (width 50 mm; thickness 0.05 mm) | 156 mm | Shield for the remote unit hub cover |
| Self-adhesive copper tape (width 8 mm; thickness 0.05 mm) | 286 mm | Side shield of the hub board |
| Sheet copper 0.8 mm thick | 100 mm x 38 mm | Large heatsink for the hub board |
| Sheet copper 0.8 mm thick | 30 mm x 19 mm | Voltage converter heatsink |
| Sheet copper 0.8 mm thick | 48 mm x 26 mm | Video amplifier heatsink |
| Silicone thermal pad 1 mm 6W/m.k | 18 mm x 16 mm | Heat dissipation from the voltage converter to the large heatsink of the hub board |
| Silicone thermal pad 1.5 mm 6W/m.k | 18 mm x 16 mm | Heat dissipation from the voltage converter to its heatsink |
| Silicone thermal pad 2 mm 6W/m.k | 30 mm x 27 mm - 2 pcs | Heat dissipation from the video amplifier to the large heatsink of the hub board |
| Silicone thermal pad 1.5 mm 6W/m.k | 27 mm x 27 mm | Heat dissipation from the video amplifier to its heatsink |
| Copper wire 20 AWG silicone insulated, black | 810 mm | |
| Copper wire 20 AWG silicone insulated, red | 810 mm | |
| Copper wire 26 AWG silicone insulated, black | 120 mm | |
| Copper wire 26 AWG silicone insulated, red | 60 mm | |
| Copper wire 26 AWG silicone insulated, green | 410 mm | |
| Copper wire 26 AWG silicone insulated, blue | 290 mm | |
| Copper wire 28 AWG silicone insulated, black | 680 mm | |
| Coaxial cable RG-316 | 500 mm | |
| Screw M2x6 DIN 7985 | 4 pcs | |
| Screw M2x8 DIN 7985 | 11 pcs | |
| Washer M2 DIN 125 | 15 pcs | |
| Nut M2 DIN 934 | 15 pcs | |
| Screw M3x18 DIN 7985 A2 | 6 pcs | |
| Screw M3x20 DIN 7985 A2 | 5 pcs | |
| Screw M3x25 DIN 965 | 3 pcs | |
| Screw M3x30 DIN 965 | 5 pcs | |
| Screw M3x40 DIN 965 | 3 pcs | |
| Washer M3 DIN 125 | 12 pcs | |
| Washer M3 DIN 9021 | 5 pcs | |
| Nut M3 DIN 934 | 22 pcs | |
| Wing nut M3 DIN 315 | 5 pcs | |
| Part 1 - 3D printing | 1 pc | |
| Part 2 - 3D printing | 1 pc | |
| Part 3 - 3D printing | 1 pc | |
| Part 4 - 3D printing | 1 pc | |

## 3D Printing Settings and Material Used

| Parameter | Value |
| :---: | :---: |
| Perimeter count | 4 |
| Top/Bottom solid layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Support | Tree |

Material: coPET black MonoFilament

## Detailed Fastener Requirements

| Part Name | Type/Size | Qty | Note |
| :--- | :--- | :---: | :---: |
| Screw | M3x25 DIN 965 | 3 pcs | Mounting the hub connector block cover |
| Screw | M3x40 DIN 965 | 3 pcs | Mounting the hub connector block cover |
| Nut | M3 DIN 934 | 6 pcs | Mounting the hub connector block cover |
| Screw | M2x8 DIN 7985 | 3 pcs | Mounting the large heatsink to the hub board |
| Washer | M2 DIN 125 | 3 pcs | Mounting the large heatsink to the hub board |
| Nut | M2 DIN 934 | 3 pcs | Mounting the large heatsink to the hub board |
| Screw | M2x8 DIN 7985 | 4 pcs | Mounting the VA-Do-2/2 module heatsink to the hub board |
| Washer | M2 DIN 125 | 4 pcs | Mounting the VA-Do-2/2 module heatsink to the hub board |
| Nut | M2 DIN 934 | 4 pcs | Mounting the VA-Do-2/2 module heatsink to the hub board |
| Screw | M2x8 DIN 7985 | 4 pcs | Mounting the mBEC 12S voltage converter heatsink to the hub board |
| Washer | M2 DIN 125 | 4 pcs | Mounting the mBEC 12S voltage converter heatsink to the hub board |
| Nut | M2 DIN 934 | 4 pcs | Mounting the mBEC 12S voltage converter heatsink to the hub board |
| Screw | M2x6 DIN 7985 | 4 pcs | Mounting the power bus board to the hub board |
| Washer | M2 DIN 125 | 4 pcs | Mounting the power bus board to the hub board |
| Nut | M2 DIN 934 | 4 pcs | Mounting the power bus board to the hub board |
| Screw | M3x18 DIN 7985 A2 | 6 pcs | Mounting the hub board to the base |
| Washer | M3 DIN 125 | 12 pcs | Mounting the hub board to the base (2 washers per screw) |
| Nut | M3 DIN 934 | 6 pcs | Mounting the hub board to the base |
| Screw | M3x30 DIN 965 | 5 pcs | Mounting the hub cover |
| Nut | M3 DIN 934 | 5 pcs | Mounting the hub cover |
| Screw | M3x20 DIN 7985 A2 | 5 pcs | Additional mounting in the hub cover |
| Washer | M3 DIN 9021 | 5 pcs | Additional mounting in the hub cover |
| Nut | M3 DIN 934 | 5 pcs | Additional mounting in the hub cover |
| Wing nut | M3 DIN 315 | 5 pcs | Additional mounting in the hub cover |


## Detailed Wire Consumption

XS1
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 170 mm | XS1 - GND bus of the hub board |
| 20 AWG red | 170 mm | XS1 - +BAT bus of the hub board |
| 26 AWG green | 150 mm | XS1 - VA-Do-2/2 |
| 26 AWG blue | 150 mm | XS1 - VA-Do-2/2 |
| 26 AWG green | 60 mm | XS1 - XS2 |
| 26 AWG blue | 60 mm | XS1 - XS2 |
| 26 AWG green | 80 mm | XS1 - XS3 |
| 26 AWG blue | 80 mm | XS1 - XS3 |

XS2
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 190 mm | XS2 - GND bus of the hub board |
| 20 AWG red | 190 mm | XS2 - +BAT bus of the hub board |

XS3
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 220 mm | XS3 - GND bus of the hub board |
| 20 AWG red | 220 mm | XS3 - +BAT bus of the hub board |
| RG-316 | 250 mm | XS3 - VA-Do-2/2 |

XS4
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 230 mm | XS4 - GND bus of the hub board |
| 20 AWG red | 230 mm | XS4 - +BAT bus of the hub board |
| RG-316 | 250 mm | XS3 - VA-Do-2/2 |

mBEC 12S Voltage Converter
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 60 mm | mBEC 12S - GND bus of the hub board |
| 26 AWG red | 60 mm | mBEC 12S - +BAT bus of the hub board |
| 26 AWG green | 60 mm | mBEC 12S - +5V bus of the hub board |

VA-Do-2/2 Module
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 60 mm | VA-Do-2/2 - GND bus of the hub board |
| 26 AWG green | 60 mm | VA-Do-2/2 - +5V bus of the hub board |
| 28 AWG black | 50 mm | VA-Do-2/2 - RG-316 cable shield from XS3 |
| 28 AWG black | 50 mm | VA-Do-2/2 - RG-316 cable shield from XS4 |

Heatsinks and Shields
| Type | Length | Note |
| :--- | :--- | :---: |
| 28 AWG black | 170 mm | Large heatsink of the hub board - GND bus of the hub board |
| 28 AWG black | 60 mm | VA-Do-2/2 module heatsink - GND bus of the hub board |
| 28 AWG black | 60 mm | mBEC 12S voltage converter heatsink - GND bus of the hub board |
| 28 AWG black | 120 mm | Side shield of the hub board - GND bus of the hub board |
| 28 AWG black | 170 mm | Front shield on the hub cover - GND bus of the hub board |
