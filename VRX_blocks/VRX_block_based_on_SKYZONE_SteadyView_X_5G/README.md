# VRX block based on SKYZONE SteadyView X 5G

The VRX block based on the Skyzone SteadyView X 5G video receiver is a functional module mounted on the remote unit and designed to receive analog video signals in the 4.9–5.9 GHz range with their subsequent feed into the ground station's switching lines. To reduce screen light emission, it is possible to install a masking cover. The appearance of the VRX block with and without the masking cover is shown in the following image.

<img width="600" alt="General view of the Skyzone SteadyView X 5G VRX unit" src="picture/general_view_of_the_Skyzone_SteadyView_X_5G_VRX_unit.png" />

## Quick technical specifications of the VRX block based on the Skyzone SteadyView X 5G video receiver

| Parameter | Value | Note |
|----------|---------|---------|
| Input voltage | 6S Li-ion/LiPo battery (Min 22.2V Max 25.2V) | Powered from the remote unit hub |
| Frequency range | 4.9–5.9 GHz |  |
| Control | Manual or remote | Via stock control elements or ELRS Backpack |
| Output video signal type | Analog composite (CVBS) | |

### Interfaces

| Connector | Purpose | Main signals | Note |
|--------|------------|----------------|----------|
| XS1 (GX12-6) | Connection to the remote unit hub | +BAT, GND, CVBS |  |

## Schematic design and functionality

Power is supplied to the VRX block via the XS1 connector from the +BAT bus of the remote unit hub. The output CVBS signal from the video receiver is transmitted via XS1 to the ground station's switching lines. 

<img width="800" alt="Schematic diagram of the VRX block based on the Skyzone SteadyView X 5G video receiver" src="schematic_diagram/schematic_diagram_vrx_block_skyzone_steadyview_x.JPG" />

The connection between the video receiver and the XS1 connector is made using copper wires with 26 AWG cross-section and silicone insulation. The red wire (+BAT) is connected to the cathode of the TVS diode (suppressor), the black wire (GND) to the negative terminal of the capacitor, and the yellow wire (CVBS) to the sixth pin of the RXPORT100 V1.1 board connector of the Skyzone SteadyView X 5G video receiver.

<img width="600" alt="Connecting wires to the RXPORT100 V1.1 board" src="picture/connecting_wires_to_the_board_RXPORT100_V1.1.jpg" />

Channel control is performed by the stock control elements of the video receiver or via the ELRS Backpack.

## List of necessary components for manufacturing one VRX block

| Component Name | Quantity | Note |
| :--- | :--- | :---: |
| VRX Skyzone SteadyView X 5G video receiver kit | 1 pc | |
| 90-degree SMA Female to SMA Male elbow adapter | 2 pcs | |
| GX12-6 pin panel mount plug (male) | 1 pc | XS1 |
| Double-sided acrylic tape 2 mm | 100 mm | Mounting the VRX Skyzone SteadyView X 5G to Part 1 |
| 2x8 self-tapping screw DIN 7982 | 8 pcs | Mounting Part 2 and Part 3 to Part 1 |
| Copper wire 26 AWG with silicone insulation, black | 150 mm | VRX Skyzone SteadyView X 5G -> XS1 |
| Copper wire 26 AWG with silicone insulation, red | 150 mm | VRX Skyzone SteadyView X 5G -> XS1 |
| Copper wire 26 AWG with silicone insulation, yellow | 150 mm | VRX Skyzone SteadyView X 5G -> XS1 |
| Part 1 - 3D print | 1 pc | |
| Part 2 - 3D print | 1 pc | |
| Part 3 - 3D print | 1 pc | |

## 3D printing settings and material used

| Parameter | Value |
| :---: | :---: |
| Wall line count (perimeters) | 4 |
| Top and bottom solid layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Supports | Tree-like |

Material: coPET black MonoFilament
