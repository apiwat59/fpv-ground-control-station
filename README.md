# Ground Control Station 'HALYT'

Ground Control Station 'HALYT' สำหรับ FPV drones เป็น modular system ที่รองรับการเปลี่ยน configuration ตามความเหมาะสมของงานและเงื่อนไขในการทำงาน

<img width="800" alt="General view of GCS 'HALYT'" src="assets/picture/ground_control_station_main_preview.jpg" />

สถาปัตยกรรมของสถานีตั้งอยู่บนหลักการของการแยกส่วนการทำงานของ system components ออกจากกัน และอนุญาตให้เพิ่ม functional expansion ได้โดยการรวม modules เพิ่มเติมโดยไม่ต้องเปลี่ยนโครงสร้างพื้นฐาน

<img width="800" alt="GCS 'HALYT' Architecture" src="assets/block_diagram/ground_station_architecture_block_diagram.JPG" />

ระบบนี้ได้รับการพัฒนาขึ้นโดยคำนึงถึงประสบการณ์การรบจริงของเรา, ความพร้อมใช้งานของ components, การสนับสนุนผู้ผลิตในประเทศอย่างสูงสุด และความเป็นไปได้สำหรับเจ้าหน้าที่ด้านเทคนิคในการทำซ้ำแบบในโรงเวิร์กชอปภาคสนามทางการทหาร พลเรือน หรืออาสาสมัครที่มีอุปกรณ์ระดับปานกลาง

แนะนำให้ทำตามลำดับขั้นตอนด้านล่างนี้สำหรับการผลิตและการประกอบระบบ:

1.	**[Universal case and station body](Universal_case_and_station_body/)**
2.	**[Station control unit](Station_control_unit/)**
3.	**[Monitor modernization](Monitor_modernization/)**
4.	**[Remote unit](Remote_unit/)**
5.	**[VRX blocks](VRX_blocks/)**
6.	**[Control_subsystem](Control_subsystem/)**
7.	**[Cables](Cables/)**

## Video Guide for Manufacturing and Assembling GCS 'HALYT'

[![GCS HALYT — Full assembly video guide](https://img.youtube.com/vi/9ohl-sQVgZU/maxresdefault.jpg)](https://www.youtube.com/watch?v=9ohl-sQVgZU)

*คลิกที่รูปภาพเพื่อรับชมวิดีโอบน YouTube*

เมื่อปฏิบัติตามคู่มือการผลิตและขั้นตอนปฏิบัติในการทำงาน ผลิตภัณฑ์ที่สมบูรณ์จะให้ระดับความแข็งแรงทางกล (mechanical strength), maintainability และคุณลักษณะการทำงานที่เทียบได้กับรุ่นที่ผลิตเพื่อการพาณิชย์ในคลาสเดียวกัน ภาพรวมทั่วไปของ Ground Control Station 'HALYT' แสดงอยู่ในภาพถ่าย

<img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_1.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_2.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_3.jpg" />

<img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_4.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_5.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_6.jpg" />

<img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_7.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_8.jpg" /> <img width="250" alt="General view of GCS 'HALYT'" src="assets/picture/general_view_ground_control_station_9.jpg" />

## License

การใช้ materials ใน repository นี้อยู่ภายใต้บังคับของ License Agreement ซึ่งมีข้อกำหนดหลักดังนี้:

- Materials จัดทำขึ้นเพื่อการใช้งานด้าน technical, educational, research หรือการใช้งานอื่นที่ไม่ใช่ในเชิงพาณิชย์เท่านั้น
- การผลิตผลิตภัณฑ์ตาม Materials ได้รับอนุญาตให้ทำได้เฉพาะการใช้งานที่ไม่ใช่ในเชิงพาณิชย์เท่านั้น โดยเฉพาะอย่างยิ่งเพื่อความต้องการในการป้องกันประเทศของยูเครน
- ห้ามใช้งาน materials การปรับปรุงแก้ไข หรือผลิตภัณฑ์ที่ผลิตขึ้นโดยอ้างอิงจาก materials ในเชิงพาณิชย์ทุกกรณี โดยไม่ได้รับความยินยอมเป็นลายลักษณ์อักษรแยกต่างหากจาก DKB-1571
- ไม่อนุญาตให้ทำการ Redistribution ของ materials และอนุญาตเฉพาะการแบ่งปัน links ไปยัง resources ทางการของ DKB-1571 เท่านั้น
- Materials ถูกจัดเตรียมให้ตามสภาพที่เป็นอยู่ ('as is') โดยที่ User ใช้งานโดยแบกรับความเสี่ยงด้วยตนเอง
- สิทธิ์ในทรัพย์สินทางปัญญาที่เป็นกรรมสิทธิ์แต่เพียงผู้เดียวของ Materials เป็นของ DKB-1571

โปรดตรวจสอบข้อตกลงสัญญาอนุญาตเวอร์ชันเต็มในไฟล์ `LICENSE.md` ของ repository นี้

---

โครงการนี้ถูกสร้างขึ้นโดยอิงจากประสบการณ์การรบจริงในการใช้งาน FPV systems

Engineer 'Trolleybus'  
Donetsk Oblast, Ukraine  
2026
