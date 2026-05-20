# Universal frame

Universal frame ได้รับการออกแบบมาสำหรับการติดตั้งและ mechanical integration ของ remote unit hub และ peripheral devices โดย remote unit hub และ peripheral devices ที่ติดตั้งอยู่บน universal frame จะประกอบกันเป็น remote unit ของ ground control station

การออกแบบ frame ช่วยรองรับ:
- การติดตั้ง remote unit hub
- การติดตั้ง TX unit และ VRX units
- การยึดชิ้นส่วนต่างๆ ของระบบเข้าด้วยกันอย่างเป็นหนึ่งเดียว
- การปรับเปลี่ยนสถานะของ remote unit อย่างรวดเร็วระหว่างตำแหน่ง transport และ operational

<img width="600" alt="General view of the remote unit" src="picture/general_view_of_the_remote_unit.png" />

## Design Features

- โครงสร้างการออกแบบมีลักษณะเป็น modular architecture
- มีพื้นที่รองรับสำหรับการติดตั้ง TX และ VRX units ที่สับเปลี่ยนกันได้
- ทุก module จะถูกยึดด้วยจุดเชื่อมต่อแบบ screw
- การออกแบบมีคุณสมบัติทนทานต่อ mechanical loads และการสั่นสะเทือน (vibrations)

## Transport Position

การจัดตำแหน่ง transport position ของ remote unit ในกล่อง ground control station ประกอบไปด้วย:
- ถอดชิ้นส่วน stand ออก
- ไม่มี VRX unit ใน auxiliary slot
- จัดตำแหน่งยึดของ peripheral devices ให้คงที่

<img width="800" alt="Transport position of the remote unit" src="picture/transport_position_of_the_remote_unit.jpg" />

## Bill of Materials for One Universal Frame

| Part Name | Qty | Note |
| :--- | :--- | :---: |
| Screw M2x10 DIN 7985 | 12 pcs | ยึด peripheral devices |
| Nut M2 DIN 934 | 12 pcs | ยึด peripheral devices |
| Screw M3x14 DIN 7985 A2 | 2 pcs | ยึด remote unit handle |
| Screw M3x20 DIN 7985 A2 | 2 pcs | ยึด stand |
| Screw M3x30 DIN 965 | 5 pcs | ยึด universal frame เข้ากับ hub |
| Nut M3 DIN 934 | 9 pcs | ยึด universal frame เข้ากับ hub, ยึด stand, ยึด remote unit handle |
| Wing nut M3 DIN 315 | 2 pcs | ยึด stand |
| Self-tapping screw 2x8 DIN 7982 | 2 pcs | ยึด antenna retainer |
| Part 1 - 3D printing | 1 pc |  |
| Part 2 - 3D printing | 1 pc |  |
| Part 3 - 3D printing | 1 pc |  |
| Part 4 - 3D printing | 1 pc |  |

## 3D Printing Settings and Material Used

| Parameter | Value |
| :---: | :---: |
| Perimeter count | 4 |
| Top/Bottom solid layers | 5 |
| Infill density | 40% |
| Infill pattern | Gyroid |
| Support | Tree |

Material: coPET black MonoFilament
