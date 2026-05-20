# Control_subsystem

The control subsystem provides two-way data exchange via the ground control station's switching lines using the RS-485 standard between the operator's control panel and the control transmitter installed in the remote unit of the ground control station.

The control subsystem includes:
- JR_module_adapter (on the control panel side)
- TX_unit (on the remote unit side)

## Brief Technical Specifications

| Parameter | Value | Note |
|----------|---------|---------|
| Control protocol | CRSF | Via S.Port |
| Transmission interface | Differential signal of the RS-485 standard | Noise-immune, long lines |
| Data transmission channel | Ground control station switching lines | Maximum length depends on cable type |
| Operating mode | Two-way | Control + telemetry |
| JR module adapter power supply | 5–8.4 V | From the control panel |
| TX unit power supply | From the remote unit hub | Via XS2 |
| Control transmitter TX module power supply | 8V | From the TX unit |
| TX unit output voltage via XS3 connector | 8V | Maximum continuous current 2A |
| Cooling | Passive | Heatsinks + ventilation holes |
| Shielding | Partial | |

## Operating Principle and Architecture

The control signal from the control panel is sent to the JR module adapter, where it is converted into a differential signal of the RS-485 standard. Next, the signal is transmitted through the ground control station's switching lines to the TX unit, where reverse conversion into a CRSF protocol signal occurs before being fed to the control transmitter. The return channel (telemetry) works similarly in the opposite direction.

<img width="800" alt="Block diagram of the control subsystem architecture" src="control_subsystem_architecture_block_diagram.JPG" />

The detailed implementation of each device of the control subsystem is given in the corresponding sections:

* **[JR_module_adapter](JR_module_adapter/)**
* **[TX_unit](TX_unit/)**
