# VRX block based on Readytosky 1.2G/1.3G

The VRX block based on the Readytosky 1.2–1.3 GHz 9CH video receiver is a functional module mounted on the remote unit and designed to receive analog video signals in the 1.2–1.3 GHz range with their subsequent feed into the ground station's switching lines.

<img width="400" alt="General view of the 1.2–1.3 GHz VRX unit" src="picture/general_view_of_the_1.2_1.3_GHz_VRX_unit.png" />

## Quick technical specifications of the VRX block based on the Readytosky 1.2–1.3 GHz 9CH video receiver

| Parameter | Value | Note |
|----------|---------|---------|
| Input voltage | 6S Li-ion/LiPo battery (Min 22.2V Max 25.2V) | Powered from the remote unit hub |
| Frequency range | 1060 - 1380 MHz | 9 channels (1080/1120/1160/1200/1240/1280/1320/1360/1258 MHz) |
| Control | Manual | Via stock channel selector |
| Output video signal type | Analog composite (CVBS) | |

### Interfaces

| Connector | Purpose | Main signals | Note |
|--------|------------|----------------|----------|
| XS1 (GX12-6) | Connection to the remote unit hub | +BAT, GND, CVBS |  |

## Schematic design and functionality

Power is supplied to the VRX block via the XS1 connector from the +BAT bus of the remote unit hub. The output CVBS signal from the video receiver is transmitted via XS1 to the switching lines of the ground control station. Channel control is performed by the stock channel selector of the video receiver. 

<img width="800" alt="Schematic diagram of the VRX block based on the Readytosky 1.2–1.3 GHz 9CH video receiver" src="schematic_diagram/schematic_diagram_vrx_block_readytosky_1.2g_1.3g.JPG" />

## List of necessary components for manufacturing one VRX block

| Component Name | Quantity | Note |
| :--- | :--- | :---: |
| Readytosky 1.2–1.3 GHz 9CH video receiver kit | 1 pc | |
| 90-degree SMA Female to SMA Male elbow adapter | 1 pc | |
| GX12-6 pin panel mount plug (male) | 1 pc | XS1 |
| M2x18 screw DIN 7985 | 1 pc | Mounting the video receiver to Part 1 |
| M2 nut DIN 934 | 1 pc | Mounting the video receiver to Part 1 |
| 2x8 self-tapping screw DIN 7982 | 8 pcs | Mounting Part 2 and Part 3 to Part 1 |
| Part 1 - 3D print | 1 pc | |
| Part 2 - 3D print | 1 pc | |
| Part 3 - 3D print | 1 pc | |
| Part 4 - 3D print | 1 pc | |

## 3D printing settings and material used

| Parameter | Value |
| :---: | :---: |
| Wall line count (perimeters) | 4 |
| Top and bottom solid layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Supports | Tree-like |

Material: coPET black MonoFilament
