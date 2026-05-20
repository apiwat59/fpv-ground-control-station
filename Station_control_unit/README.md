# Station control unit

Station control unit ใช้สำหรับ power distribution and switching, signal concentration, และ signal switching ระหว่าง remote unit และ peripheral devices

<img width="800" alt="General view of the control unit" src="picture/general_view_of_the_control_unit_gcs.png" />

## Quick technical specifications of the station control unit

| Parameter | Value | Note |
|----------|---------|---------|
| Input voltage | แบตเตอรี่ 6S Li-ion/LiPo (Min 22.2V Max 25.2V) | ผ่าน XT60 |
| Power protection | Fuse 5A | FU1 |
| Power switching | Toggle switches | SA1 (station main power), SA2 (remote unit power) |
| Power bus | +BAT | ตรงจากแบตเตอรี่ |
| Auxiliary buses | +12V, +5V | สร้างโดย DC-DC converters |
| Max current on the +12V bus | สูงสุด 3 A | โหลดทั้งหมด (Total load) |
| Number of video inputs | 1 (พร้อมตัวเลือกในการเลือก active video input บน remote unit) | Toggle switch SA3 |
| Input video signal type | Analog differential | |
| Number of video outputs | 4 | XS4–XS7 |
| Output video signal type | Analog composite (CVBS) | |
| Video processing | Amplification / conversion / splitting / filtering | VA-Di-2/4 module |
| Video level adjustment | มี | R1 potentiometer |
| Video noise filtering | มี | Toggle switch SA4 |
| BYPASS mode | มี | Connectors XS8–XS9 |
| TX interface | มี | ผ่าน XS2 |
| VRX control | รองรับ | ผ่าน XS3 |
| Cooling | Passive | Copper heatsinks + ช่องระบายอากาศ |
| Shielding | Partial | Shielding ของ voltage converters ด้วย copper heatsinks |

### Interfaces

| Connector | Purpose | Main signals | Note |
|--------|------------|----------------|----------|
| XS1 (GX20-8) | การเชื่อมต่อกับ Remote unit | +BAT, GND, differential lines | ช่องทางการสื่อสารหลัก (Main communication channel) |
| XS2 (GX12-6) | Remote control (TX) | +BAT, GND, differential line | |
| XS3 (GX12-6) | VRX1 / remote unit peripheral control | +BAT, GND, differential line | ตัวเลือกเพิ่มเติม (Optional) |
| XS4 (GX12-6) | Video output 1 | +BAT, +12V, GND, CVBS | Monitor, goggles, DVR video recorder, video capture card สำหรับ streaming, ฯลฯ |
| XS5 (GX12-6) | Video output 2 | +BAT, +12V, GND, CVBS | Monitor, goggles, DVR video recorder, video capture card สำหรับ streaming, ฯลฯ |
| XS6 (GX12-6) | Video output 3 | +BAT, +12V, GND, CVBS | Monitor, goggles, DVR video recorder, video capture card สำหรับ streaming, ฯลฯ |
| XS7 (GX12-6) | Video output 4 (monitor) | +BAT, +12V, GND, CVBS | การเชื่อมต่อ Monitor |
| XS8 (GX12-6) | BYPASS (output) | +BAT, +12V, GND, CVBS | การเชื่อมต่อตรง (Direct connection) |
| XS9 (GX12-6) | BYPASS (input) | +BAT, +12V, GND, CVBS | แหล่งสัญญาณ (Signal source) |
| XT60 | Power input | +BAT, GND | ผ่าน Fuse |

## Schematic design and functionality of the station control unit

<img width="800" alt="Schematic diagram of the control unit" src="schematic_diagram/schematic_diagram_of_the_control_unit_gcs.JPG" />

แหล่งจ่ายไฟถูกส่งไปยัง control unit จากแบตเตอรี่ 6S3P Li-ion/LiPo ผ่าน fuse FU1 ขนาด 5A และจ่ายไปที่ toggle switch SA1 การเปิด toggle switch SA1 จะเป็นการจ่ายไฟไปยังบัส +BAT ซึ่งจ่ายพลังงานทั่วไปให้กับ ground control station

remote unit เชื่อมต่อกับ control unit ผ่านสาย cables ทาง connector XS1 ตัว remote control เชื่อมต่อผ่าน JR module ด้วยตัวแปลง CRSF -> RS-485 ไปยัง connector XS2 ส่วน connector XS3 จะใช้เมื่อต้องการ remote control ของ video receiver ผ่านสาย twisted pair (โปรดทราบว่าฟังก์ชันนี้ใช้ได้เฉพาะกับ video input ช่องที่ 1 ของ remote unit เท่านั้น) หากจำเป็น สามารถใช้สาย twisted pair จาก connector XS3 เพื่อส่งสัญญาณควบคุมไปยัง peripheral devices อื่นๆ ของ remote unit ได้ พลังงานจะถูกจ่ายไปยัง connectors XS1, XS2, และ XS3 จากบัส +BAT ผ่าน toggle switch SA2

การเชื่อมต่อของอุปกรณ์ peripheral video (เช่น monitor, goggles, DVR video recorder, video capture card สำหรับ streaming ฯลฯ) จะทำผ่าน connectors XS4, XS5, XS6, และ XS7 โดย connector XS7 จะถูกจองไว้สำหรับ monitor ที่ติดตั้งภายในตัวสถานี connectors XS4, XS5, XS6, และ XS7 จะรับพลังงานจากบัส +BAT และ +12V สัญญาณ video ไปยัง connectors XS4, XS5, XS6, และ XS7 มาจาก active video amplifier-splitter ซึ่งใช้ไฟเลี้ยงจากบัส +5V โดยมีตัวเลือกในการเลือก active video input บน remote unit (toggle switch SA3), ฟังก์ชันลดสัญญาณรบกวน (noise reduction) เมื่อมีสัญญาณรบกวนรุนแรง (toggle switch SA4), และการปรับระดับ video (video level adjustment) ผ่านตัวต้านทานปรับค่าได้ R1 (video level)

หากจำเป็นต้องส่งสัญญาณ video ไปยัง monitor โดยตรง สามารถใช้ตัวเลือก "BYPASS" ได้ (connectors XS8 และ XS9) โดยการเชื่อมต่อ monitor เข้ากับ connector XS8 และเชื่อมต่อแหล่งสัญญาณ video เข้ากับ connector XS9 ส่วนพลังงานจะถูกจ่ายไปยัง connectors XS8 และ XS9 จากบัส +BAT และ +12V

พลังงานของบัส +12V และ +5V ได้มาจาก voltage converters การระบายความร้อนจาก converters จะใช้ copper heatsinks จำนวนสองตัวผ่าน silicone thermal interface ตัว copper heatsinks จะเชื่อมต่อเข้ากับสายกราวด์ร่วม (GND) และเมื่อทำงานร่วมกับตัวเก็บประจุแบบเซรามิก (ceramic capacitors) ที่เอาต์พุตของ voltage converters จะช่วยลดสัญญาณรบกวน (parasitic noise) จากการทำงานของ converters ให้เหลือน้อยที่สุด โหลดต่อเนื่องทั้งหมดบนบัส +12V ผ่าน connectors XS4, XS5, XS6, XS7, XS8, และ XS9 จะต้องไม่เกิน 3A

station control unit มีความหนาแน่นของอุปกรณ์ (component density) สูง และต้องทำงานกับระดับแรงดันไฟฟ้าที่หลากหลาย ความสำเร็จในการประกอบอุปกรณ์นี้ต้องอาศัยทักษะการอ่าน schematic และประสบการณ์ในการประกอบงานที่มีความซับซ้อนระดับปานกลาง

<img width="600" alt="Assembly process of the control unit" src="picture/installation_view.jpg" />

## List of necessary components for manufacturing one control unit

| Component Name | Quantity | Note |
| :--- | :--- | :---: |
| 100DP1T1B1M1QEH toggle switch หรือ MTS-202 6-pin ON-ON ที่หาได้ทั่วไป | 4 ชิ้น | SA1-SA4 (หมายเหตุ: toggle switches ที่หาได้ทั่วไปต้องได้รับการปรับแต่งเพื่อความน่าเชื่อถือในการสลับสัญญาณ!) |
| WH148 1 kOhm potentiometer | 1 ชิ้น | ตัวปรับระดับ video (Video level regulator) |
| WH148 potentiometer knob | 1 ชิ้น | |
| VideoLink VA-Di-2/4 video amplifier-splitter | 1 ชิ้น | โมดูลที่ผลิตในยูเครน [สั่งซื้อ VideoLink VA-Di-2/4 จากผู้ผลิต](https://sezam.video/shop/videopidsilyuvach-videolink-va-di-24/) |
| GUTI ELECTRONICS BEC12S-PRO voltage converter | 1 ชิ้น | อุปกรณ์สัญชาติยูเครนที่เทียบเท่า Matek BEC 12S PRO [สั่งซื้อ GUTI ELECTRONICS BEC12S-PRO จากผู้ผลิต](https://prom.ua/ua/p2814749849-otechestvennyj-analog-matek.html) |
| GUTI ELECTRONICS mBEC12S voltage converter | 1 ชิ้น | อุปกรณ์สัญชาติยูเครนที่เทียบเท่า Matek BEC 12S [สั่งซื้อ GUTI ELECTRONICS mBEC12S จากผู้ผลิต](https://prom.ua/ua/p2814749850-otechestvennyj-analog-matek.html) |
| DSN-DVM-368 0-30V voltmeter | 1 ชิ้น | |
| GX20-8 pin panel mount plug (male) | 1 ชิ้น | XS1 |
| GX12-6 pin panel mount plug (male) | 8 ชิ้น | XS2-XS9 |
| XT60E-M connector | 1 ชิ้น | |
| FH-501 (KLS5-701) fuse holder | 1 ชิ้น | |
| FT Standard 5A fuse | 1 ชิ้น | |
| แผ่นทองแดงหนา 0.8 mm | 134 mm x 40 mm | Cooling heatsinks สำหรับ power distribution module |
| Silicone thermal pad 1.5 mm 6W/m.k | 84 mm x 24 mm | การระบายความร้อนจาก voltage converters ไปยัง cooling heatsinks |
| Silicone thermal pad 1 mm 6W/m.k | 18 mm x 16 mm | การระบายความร้อนจาก voltage converters ไปยัง cooling heatsinks |
| แผ่นไฟเบอร์กลาสเคลือบทองแดงหน้าเดียว (FR4) 1.5 mm | 35 mm x 17 mm | บอร์ด power bus ใน power distribution module |
| สายไฟทองแดง 26 AWG หุ้มฉนวนซิลิโคน, สีดำ | 760 mm | |
| สายไฟทองแดง 26 AWG หุ้มฉนวนซิลิโคน, สีแดง | 250 mm | |
| สายไฟทองแดง 26 AWG หุ้มฉนวนซิลิโคน, สีเหลือง | 490 mm | |
| สายไฟทองแดง 26 AWG หุ้มฉนวนซิลิโคน, สีน้ำเงิน | 410 mm | |
| สายไฟทองแดง 26 AWG หุ้มฉนวนซิลิโคน, สีเขียว | 660 mm | |
| สายไฟทองแดง 20 AWG หุ้มฉนวนซิลิโคน, สีดำ | 1540 mm | |
| สายไฟทองแดง 20 AWG หุ้มฉนวนซิลิโคน, สีแดง | 2140 mm | |
| สายไฟทองแดง 20 AWG หุ้มฉนวนซิลิโคน, สีเหลือง | 1060 mm | |
| สกรู M2x8 DIN 7985 | 14 ชิ้น | |
| สกรู M2.5x8 DIN 965 | 2 ชิ้น | |
| สกรู M2.5x12 DIN 7985 | 2 ชิ้น | |
| สกรู M3x8 DIN 7985 A2 | 2 ชิ้น | |
| สกรู M3x16 DIN 7985 A2 | 4 ชิ้น | |
| แหวนรอง M2 DIN 125 | 14 ชิ้น | |
| แหวนรอง M2.5 DIN 125 | 2 ชิ้น | |
| แหวนรอง M3 DIN 125 | 2 ชิ้น | |
| น็อตตัวเมีย M2 DIN 934 | 14 ชิ้น | |
| น็อตตัวเมีย M2.5 DIN 934 | 2 ชิ้น | |
| น็อตตัวเมีย M3 DIN 934 | 6 ชิ้น | |
| สกรูเกลียวปล่อย 2x8 DIN 7982 | 8 ชิ้น | |
| Part 1 - 3D print | 1 ชิ้น | |
| Part 2 - 3D print | 1 ชิ้น | |
| Part 3 - 3D print | 1 ชิ้น | |
| Part 4 - 3D print | 1 ชิ้น | |

## 3D printing settings and material used

| Parameter | Value |
| :---: | :---: |
| Wall line count (perimeters) | 4 |
| Top and bottom solid layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Supports | Tree-like |

Material: coPET black MonoFilament

## Modernization of MTS-202 toggle switches (6-pin, ON-ON)

การหาซื้อ toggle switches คุณภาพสูงอาจเป็นเรื่องยาก แต่รุ่นที่หาได้ทั่วไปสามารถนำมาดัดแปลงให้ทำงานได้อย่างน่าเชื่อถือได้อย่างง่ายดาย การทำ modernization นี้ช่วยปรับปรุงความน่าเชื่อถือในการสลับสัญญาณ

### Steps for performing the work:

1. **Disassembly:** ถอดประกอบ toggle switch อย่างระมัดระวังโดยการดัดแท็บโลหะของตัว housing กลับขึ้นมา

<img width="400" alt="Disassembled MTS-202 toggle switch" src="picture/modernization_of_toggle_switches_1.jpg" />

2. **Contact preparation:** ถอด rocker arms (moving contacts) ออกมาแล้วดัดให้โค้งงอเล็กน้อยเพื่อให้สัมผัสกันได้อย่างมั่นคง

<img width="400" alt="Rocker arm (moving contact) of the MTS-202 toggle switch" src="picture/modernization_of_toggle_switches_2.jpg" /> <img width="400" alt="Modernized rocker arm (moving contact) of the MTS-202 toggle switch" src="picture/modernization_of_toggle_switches_3.jpg" />

3. **Lubrication:** เพื่อลดการสึกหรอและปรับปรุงความลื่นไหลในการเลื่อน ให้ทาจาระบีซิลิโคนหนา (thick silicone grease) ปริมาณเล็กน้อยลงบนตัวผลักพลาสติก (plastic pusher) ของ toggle switch
4. **Assembly:** ประกอบ toggle switch กลับคืนในลำดับย้อนกลับ แล้วยึดฝาครอบโลหะให้แน่นด้วยแท็บโลหะ
5. **Testing:** ตรวจสอบการทำงานของ toggle switch โดยใช้ multimeter

## Detailed list of hardware usage

| Component Name | Type/Size | Quantity | Note |
| :--- | :--- | :---: | :---: |
| Screw | M2x8 DIN 7985 | 4 ชิ้น | การยึด power bus PCB เข้ากับ Part 4 |
| Screw | M2x8 DIN 7985 | 10 ชิ้น | การยึด heatsinks เข้ากับ Part 4 |
| Screw | M2.5x8 DIN 965 | 2 ชิ้น | การยึด XT60 power connector เข้ากับ Part 1 |
| Screw | M2.5x12 DIN 7985 | 2 ชิ้น | การยึด voltmeter เข้ากับ Part 2 |
| Screw | M3x8 DIN 7985 A2 | 2 ชิ้น | การยึด fuse holder เข้ากับ Part 1 |
| Screw | M3x16 DIN 7985 A2 | 4 ชิ้น | การยึด power distribution module เข้ากับ Part 3 |
| Washer | M2 DIN 125 | 4 ชิ้น | การยึด power bus PCB เข้ากับ Part 4 |
| Washer | M2 DIN 125 | 10 ชิ้น | การยึด heatsinks เข้ากับ Part 4 |
| Washer | M2.5 DIN 125 | 2 ชิ้น | การยึด voltmeter เข้ากับ Part 2 |
| Washer | M3 DIN 125 | 2 ชิ้น | การยึด power distribution module เข้ากับ Part 3 |
| Nut | M2 DIN 934 | 4 ชิ้น | การยึด power bus PCB เข้ากับ Part 4 |
| Nut | M2 DIN 934 | 10 ชิ้น | การยึด heatsinks เข้ากับ Part 4 |
| Nut | M2.5 DIN 934 | 2 ชิ้น | การยึด voltmeter เข้ากับ Part 2 |
| Nut | M3 DIN 934 | 2 ชิ้น | การยึด fuse holder เข้ากับ Part 1 |
| Nut | M3 DIN 934 | 4 ชิ้น | การยึด power distribution module เข้ากับ Part 3 |
| Screw | 2x8 DIN 7982 | 4 ชิ้น | การยึด Part 2 เข้ากับ Part 1 |
| Screw | 2x8 DIN 7982 | 4 ชิ้น | การยึด Part 3 เข้ากับ Part 1 |

## Detailed list of wire usage

### XS1
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 100 mm | XS1 - บัส GND ของ power distribution module |
| 20 AWG red | 160 mm | XS1 - SA2 |
| 26 AWG green | 110 mm | XS1 - VA-Di-2/4 |
| 26 AWG blue | 110 mm | XS1 - VA-Di-2/4 |

### XS2
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 140 mm | XS2 - บัส GND ของ power distribution module |
| 20 AWG red | 110 mm | XS2 - SA2 |
| 26 AWG green | 100 mm | XS2 - XS1 |
| 26 AWG blue | 100 mm | XS2 - XS1 |

### XS3
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 140 mm | XS3 - บัส GND ของ power distribution module |
| 20 AWG red | 110 mm | XS3 - SA2 |
| 26 AWG green | 100 mm | XS3 - XS1 |
| 26 AWG blue | 100 mm | XS3 - XS1 |

### XS4
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 150 mm | XS4 - บัส GND ของ power distribution module |
| 20 AWG red | 150 mm | XS4 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 150 mm | XS4 - บัส +12V ของ power distribution module |
| 26 AWG yellow | 110 mm | XS4 - VA-Di-2/4 |

### XS5
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 150 mm | XS5 - บัส GND ของ power distribution module |
| 20 AWG red | 150 mm | XS5 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 150 mm | XS5 - บัส +12V ของ power distribution module |
| 26 AWG yellow | 100 mm | XS5 - VA-Di-2/4 |

### XS6
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 160 mm | XS6 - บัส GND ของ power distribution module |
| 20 AWG red | 160 mm | XS6 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 160 mm | XS6 - บัส +12V ของ power distribution module |
| 26 AWG yellow | 100 mm | XS6 - VA-Di-2/4 |

### XS7
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 170 mm | XS7 - บัส GND ของ power distribution module |
| 20 AWG red | 170 mm | XS7 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 170 mm | XS7 - บัส +12V ของ power distribution module |
| 26 AWG yellow | 110 mm | XS7 - VA-Di-2/4 |

### XS8
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 170 mm | XS8 - บัส GND ของ power distribution module |
| 20 AWG red | 170 mm | XS8 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 170 mm | XS8 - บัส +12V ของ power distribution module |
| 26 AWG yellow | 70 mm | XS8 - XS9 |

### XS9
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 160 mm | XS9 - บัส GND ของ power distribution module |
| 20 AWG red | 160 mm | XS9 - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 160 mm | XS9 - บัส +12V ของ power distribution module |

### XT60
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG black | 100 mm | XT60 - บัส GND ของ power distribution module |
| 20 AWG red | 50 mm | XT60 - Fuse holder |

### Fuse holder
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG red | 120 mm | Fuse holder - SA1 |

### Voltmeter
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 170 mm | Voltmeter - บัส GND ของ power distribution module |
| 26 AWG red | 170 mm | Voltmeter - บัส +BAT ของ power distribution module |

### SA1
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG red | 170 mm | SA1 - บัส +BAT ของ power distribution module |
| 20 AWG red | 100 mm | SA1 - SA1 jumpers |

### SA2
| Type | Length | Note |
| :--- | :--- | :---: |
| 20 AWG red | 170 mm | SA2 - บัส +BAT ของ power distribution module |
| 20 AWG red | 100 mm | SA2 - SA2 jumpers |

### SA3
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 100 mm | SA3 - VA-Di-2/4 |
| 26 AWG black | 30 mm | SA3 - SA4 |
| 26 AWG blue | 100 mm | SA3 - VA-Di-2/4 |

### SA4
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG green | 100 mm | SA4 - VA-Di-2/4 |

### R1
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 30 mm | R1 - VA-Di-2/4 |

### VA-Di-2/4
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 170 mm | VA-Di-2/4 - บัส GND ของ power distribution module |
| 26 AWG green | 170 mm | VA-Di-2/4 - บัส +5V ของ power distribution module |

### Power distribution module
| Type | Length | Note |
| :--- | :--- | :---: |
| 26 AWG black | 80 mm | Large heatsink - บัส GND ของ power distribution module |
| 26 AWG black | 80 mm | Small heatsink - บัส GND ของ power distribution module |
| 26 AWG black | 80 mm | 12S voltage converter - บัส GND ของ power distribution module |
| 26 AWG red | 80 mm | 12S voltage converter - บัส +BAT ของ power distribution module |
| 26 AWG green | 80 mm | 12S voltage converter - บัส +5V ของ power distribution module |
| 20 AWG black | 100 mm | 12S PRO voltage converter - บัส GND ของ power distribution module |
| 20 AWG red | 100 mm | 12S PRO voltage converter - บัส +BAT ของ power distribution module |
| 20 AWG yellow | 100 mm | 12S PRO voltage converter - บัส +12V ของ power distribution module |
