# VRX Blocks

This section contains documentation, 3D models, schematics, and instructions for manufacturing interchangeable video receiver units (VRX blocks) used as part of the Ground Control Station. Each VRX block is a functionally complete module designed to operate in a specific frequency band, transmission standard, or with a specific type of video receiver equipment.

## Purpose

VRX blocks provide:
- video signal reception
- transmission of the output video signal to the switching lines of the Ground Control Station
- mechanical integration of the video receiver equipment into the remote unit of the station
- unified power and signal lines connection

## Architecture and Implementation Details

### The architecture supports the use of:
<ul>
<li>analog video receivers</li>
<li>digital video receiver systems combined with a video signal converter</li>
<li>video receiver control via the Ground Control Station switching lines</li>
</ul>

<img width="800" alt="VRX blocks architecture block diagram" src="VRX_block_architecture.JPG" />

### Implementation Details
<ul>
<li>All VRX blocks have a unified connection to the remote unit hub</li>
<li>New VRX blocks integrate into the Ground Control Station without altering the architecture of other subsystems</li>
<li>Each VRX block is designed for a specific type of video receiver equipment or transmission standard</li>
<li>The design ensures VRX blocks can be replaced without modifying other components of the station</li>
</ul>
