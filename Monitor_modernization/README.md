# Monitor Modernization

universal monitor ขนาดหน้าจอ 10.1 นิ้ว ถูกนำมาใช้งานเป็นอุปกรณ์แสดงผลมาตรฐานใน ground station การใช้ monitor ประเภทนี้เหมาะสมเนื่องจากความแพร่หลายในท้องตลาด ทั้งเรื่องจำนวนสินค้าและราคา รวมถึงความลงตัวของคุณลักษณะเฉพาะทางเทคนิค มีรุ่นที่รองรับทั้ง analog video input และช่องสัญญาณ input เพิ่มเติมอื่นๆ รวมถึงดิจิทัล HDMI input การใช้ monitor ที่มีช่องสัญญาณดิจิทัล HDMI video input เพิ่มเติมใน ground station จะช่วยขยายขอบเขตการใช้งานให้หลากหลายขึ้น ตัวอย่างเช่น สามารถเชื่อมต่อ modules อย่าง Walksnail Avatar VRX และ Walksnail Ascent VRX หรือ single-board computers อย่าง Raspberry Pi เข้ากับ monitor ได้โดยตรง

<img width="800" alt="General view of the monitor" src="picture/monitor.jpg" />

monitor รุ่นนี้มีโหมด "blue screen" ที่จะทำงานเมื่อไม่มีสัญญาณวิดีโอบน active video input หรือเมื่อสัญญาณมีความผิดเพี้ยนไปอย่างมาก (significant distortion) ซึ่งเมื่อใช้ดิจิทัล HDMI video input โหมดนี้จะไม่มีผลใดๆ แต่เมื่อใช้ analog video input ความสามารถในการมองเห็นภาพผ่านสัญญาณรบกวน (noise) ถือเป็นเรื่องที่สำคัญอย่างยิ่ง

## Monitor Modernization - Theoretical Background

ปัญหา "blue screen" สามารถแก้ไขได้โดยการทำ modernization เล็กน้อยกับตัว monitor ซึ่งประกอบด้วยการประมวลผลสัญญาณวิดีโอเพิ่มเติมด้วย AT7456E chip เพื่อลดความซับซ้อนในขั้นตอนการดำเนินการให้มากที่สุด จึงเลือกใช้ flight controller ซึ่งได้รับการติดตั้งชิปตัวนี้พร้อมกับวงจรสนับสนุนอื่นๆ มาเรียบร้อยแล้ว ความเหมาะสมในการเลือกใช้ flight controller ยังมาจากการที่สามารถจัดหาได้ง่ายในภาคสนามหรือเวิร์กช็อปทั่วไป

หลักการทำงาน:
สัญญาณ output จากตัวรับสัญญาณวิดีโอ (video receiver) จะถูกประมวลผลโดย AT7456E chip ซึ่งชิป AT7456E จะช่วยคืนค่าและรักษาเสถียรภาพของการซิงโครไนซ์สัญญาณ (stabilizes synchronization) ทำให้เกิดสัญญาณ composite video signal ที่ถูกต้องที่ฝั่ง output แม้ว่าจะมีสัญญาณรบกวน (interference) ในระดับที่สูงมากก็ตาม

<img width="800" alt="Block diagram" src="schematic_diagram/block_diagram.JPG" />

สำหรับตัว monitor แล้ว สัญญาณในลักษณะนี้จะดูเป็นสัญญาณที่ "ถูกต้อง" เสมอ ดังนั้นแม้ว่าภาพจาก drone จะเต็มไปด้วย noise หรือเกือบจะหายไปทั้งหมด monitor ก็จะไม่ตัดเข้าสู่โหมด "blue screen"

ผลลัพธ์: เรายังคงสามารถเห็นภาพได้จนถึงช่วงสุดท้ายโดยที่ monitor ไม่เปลี่ยนเข้าสู่โหมด "blue screen" ซึ่งมีความสำคัญอย่างวิกฤตเมื่อเกิดสัญญาณรบกวนที่รุนแรง

<img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_1.jpg" /> <img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_2.jpg" />
<img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_3.jpg" /> <img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_4.jpg" />
<img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_5.jpg" /> <img width="400" alt="Block diagram" src="picture/image_with_different_input_signal_quality_6.jpg" />

หากสัญญาณส่วนใหญ่ประกอบไปด้วย static noise ("snow") monitor ก็อาจจะยังคงเปลี่ยนเข้าสู่โหมด "blue screen" ได้ ในกรณีนี้ คุณสามารถเชื่อมต่อแว่น goggles เข้ากับ station control unit ผ่าน connector XS4, XS5 หรือ XS6 แม้ว่าโอกาสในการสกัดสัญญาณที่เป็นประโยชน์ออกมาจากสัญญาณรบกวนที่ต่อเนื่องนั้นจะเป็นไปได้ยากก็ตาม

การปรากฏข้อความ "AV 1 PAL" ขึ้นอย่างต่อเนื่องบนพื้นหลังที่มี noise รุนแรง ถือเป็นสัญญาณบ่งชี้ว่าระบบกำลังทำงานอยู่ที่ขีดจำกัดสูงสุด นี่คือสัญญาณเตือนผู้ปฏิบัติงาน (operator): ระบบการรักษาเสถียรภาพสัญญาณซิงโครไนซ์ของ AT7456E chip ยังคงพยายามประคองอยู่ แต่ในเวลาใดก็ตาม monitor อาจตัดเข้าสู่โหมด "blue screen" เนื่องจากฝั่ง input ของชิปได้รับ noise เข้ามามากเกินไป

ทันทีที่มีสัญญาณที่เป็นประโยชน์เพียงเล็กน้อยที่สามารถระบุได้ปรากฏขึ้นในกระแสสัญญาณรบกวน ชิป AT7456E จะทำการฟื้นฟูการซิงโครไนซ์ในทันที และภาพบน monitor จะกลับมาปรากฏขึ้นอีกครั้ง

## Monitor Modernization - Practical Implementation

การปรับปรุงใช้งานจริงประกอบด้วยการประกอบวงจรดังต่อไปนี้:

<img width="800" alt="Monitor modernization diagram" src="schematic_diagram/monitor_upgrade_diagram.JPG" />

ในด้านโครงสร้าง flight controller จะถูกบรรจุอยู่ภายใน monitor housing และยึดให้แน่นหนาโดยใช้สกรูและน็อต M3

เนื่องจากการทำงานในพื้นที่ปิด จึงแนะนำให้ติดตั้ง copper heatsink เพื่อรักษาระดับอุณหภูมิ (temperature modes) ของชิป AT7456E และ microcontroller ของ flight controller โดยการถ่ายเทความร้อนไปยัง heatsink จะทำผ่าน silicone thermal interface ภาพเขียนแบบของ copper heatsink แสดงอยู่ด้านล่างนี้

<img width="400" alt="Flight controller heatsink drawing" src="drawing/fc_radiator_drawing.JPG" />

copper heatsink จะถูกเชื่อมต่อเข้ากับ common ground wire และทำหน้าที่เป็นแผงป้องกันเพิ่มเติม (additional shielding) สำหรับ AT7456E chip ส่วนชีลด์ (shield connection) ของสายเคเบิล UL2547 4x0.3mm2 (22AWG) จะเชื่อมต่อเข้ากับ common ground เฉพาะทางฝั่ง connector เท่านั้น เพื่อป้องกันไม่ให้เกิด ground loop

<img width="400" alt="Monitor modernization process" src="picture/modernization_monitor_1.jpg" /> <img width="400" alt="Monitor modernization process" src="picture/modernization_monitor_2.jpg" />

**ข้อมูลสำคัญเพิ่มเติม:** โปรดมั่นใจว่าได้ตั้งค่ามาตรฐาน PAL ในการตั้งค่าของ monitor, OSD menu ของ flight controller และการตั้งค่าสัญญาณ output ของกล้อง สำหรับการตรวจติดตามแรงดันไฟฟ้าของบัส +12V ที่จ่ายพลังงานให้กับ monitor คุณสามารถตั้งค่าการแสดงแรงดันนี้ในส่วนการตั้งค่า OSD menu ของ flight controller ได้ และด้วยเงื่อนไขสภาพการใช้งาน ขอแนะนำให้ป้องกันหน้าจอ LCD ด้วย hydrogel film ซึ่งสามารถติดได้โดยง่ายในขั้นตอนแยกชิ้นส่วนเพื่อประกอบตัว monitor

## List of Necessary Components for the Modernization of One Monitor

| Name | Quantity | Note |
|:---: | :---: | :---: |
| Flight controller with AT7456E | 1 pc | | 
| Damping standoff for flight controller M3*8 mm | 4 pcs |  | 
| Damping standoff for flight controller M3*4 mm | 4 pcs |  | 
| Screw M3x18 DIN 7985 A2 | 4 pcs | ยึด flight controller และ cooling heatsink เข้ากับ monitor housing | 
| Nut M3 DIN 934 | 4 pcs | ยึด flight controller และ cooling heatsink เข้ากับ monitor housing | 
| Silicone thermal pad 4 mm 3.5W\m.k | 25 mm x 20 mm | การถ่ายเทความร้อนจากชิป AT7456E และ STM32 ไปยัง copper heatsink | 
| Sheet copper 0.8 mm thick | 37.5 mm x 37.5 mm | Cooling heatsink | 
| Copper wire 26 AWG with silicone insulation, black | 310 mm | สายเคเบิล UL2547 -> FC = 120 mm; FC -> monitor = 210 mm | 
| Copper wire 26 AWG with silicone insulation, yellow | 330 mm | FC -> monitor = 210 mm; FC -> copper heatsink = 100 mm |
| Copper wire 26 AWG with silicone insulation, red | 100 mm | monitor -> FC |
| Copper shielded cable UL2547 4x0.3mm2 (22AWG) | 365 mm | การแบ่งความยาว: 85 mm ภายใน monitor และ 280 mm ภายนอก monitor |
| GX12-6 pin cable socket (female) | 1 pc |  |
| Hydrogel film for monitor protection | 225 mm x 128 mm |  |
