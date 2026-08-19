# 📚 Software Engineering (SE) Midterm Comprehensive Wiki (ฉบับปี 68)
> **แหล่งข้อมูลอ้างอิง:** สกัดและเรียบเรียงจากคลังเอกสาร **`New_68`** ครบถ้วน 100% 
> (Ch1 Introduction, Ch2 SW Processes, Ch4 Req Eng, Homework 1 PizzaFriend, Homework 2 EasyClinic, เอกสารการบ้าน และบันทึกท้ายคาบ)

---

## 📑 สารบัญเนื้อหา (Table of Contents)
1. [บทที่ 1: Introduction to Software Engineering](#บทที่-1-introduction-to-software-engineering)
   - 1.1 นิยามและพื้นฐานวิศวกรรมซอฟต์แวร์ (What is SE?)
   - 1.2 4 คุณลักษณะสำคัญของซอฟต์แวร์ที่ดี (4 Essential Attributes of Good Software)
   - 1.3 ความแตกต่างระหว่าง CS vs SE vs System Engineering
   - 1.4 4 กิจกรรมพื้นฐานของกระบวนการพัฒนา (4 Fundamental Process Activities)
   - 1.5 โครงสร้างต้นทุนของซอฟต์แวร์ (Software Engineering Costs)
   - 1.6 ประเภทของผลิตภัณฑ์ซอฟต์แวร์ (Generic vs Customized Products)
   - 1.7 ประเภทของแอปพลิเคชัน (8 Application Types)
   - 1.8 วิศวกรรมซอฟต์แวร์บนอินเทอร์เน็ตและเว็บ (Internet & Web-Based SE)
   - 1.9 จรรยาบรรณวิชาชีพและประเด็นความรับผิดชอบ (Professional Responsibility)
   - 1.10 จรรยาบรรณวิศวกรซอฟต์แวร์ 8 ประการ (ACM/IEEE Code of Ethics - 8 Principles)
   - 1.11 4 กรณีศึกษาประจำวิชา (4 Standard Case Studies)
2. [บทที่ 2: Software Processes](#บทที่-2-software-processes)
   - 2.1 นิยามของ Software Process และองค์ประกอบในการอธิบาย
   - 2.2 Plan-Driven vs Agile Processes
   - 2.3 ตารางเปรียบเทียบ 3 โมเดลการพัฒนาซอฟต์แวร์หลัก (Waterfall vs Incremental vs Reuse-Oriented)
   - 2.4 กิจกรรมการออกแบบระบบ (Design Process Activities)
   - 2.5 ลำดับขั้นการทดสอบระบบ (Testing Stages) & Plan-Driven V-Model
   - 2.6 วิวัฒนาการของซอฟต์แวร์ (Software Evolution Cycle)
   - 2.7 การรับมือกับการเปลี่ยนแปลง (Coping with Change & Throw-away Prototyping)
   - 2.8 วงจรการปรับปรุงกระบวนการและ 5 ระดับวุฒิภาวะ (SEI CMM Levels)
3. [บทที่ 4: Requirements Engineering](#บทที่-4-requirements-engineering)
   - 4.1 นิยามและระดับการแปลงความต้องการ (Davis Abstraction)
   - 4.2 User Requirements vs System Requirements
   - 4.3 การจำแนกประเภทความต้องการ 4 ด้าน (FR, NFR, Domain, Constraints)
   - 4.4 ผังกระบวนการวิศวกรรมความต้องการ (Spiral RE Process)
   - 4.5 เทคนิคการรวบรวมความต้องการ (Elicitation Techniques: Interviews, Ethnography, Scenarios)
   - 4.6 รูปแบบการเขียนเอกสารระบุความต้องการ (Specification Formats: Form-based, Tabular, UML)
   - 4.7 การตรวจสอบความถูกต้องของข้อกำหนด (Requirements Validation Checks: V-C-C-R-V)
   - 4.8 กระบวนการจัดการการเปลี่ยนแปลงความต้องการ (Requirements Change Management)
4. [คลังเฉลยการบ้านและบันทึกข้อสอบ (Homework & Lecture Q&A Repository)](#คลังเฉลยการบ้านและบันทึกข้อสอบ)
   - 4.1 เฉลยการบ้าน 1: PizzaFriend Requirements
   - 4.2 เฉลยการบ้าน 2: EasyClinic 9 Stakeholders & Roles
   - 4.3 การบ้านการสะท้อนจริยธรรม 4 ด้าน ("ฉันจะ...")
   - 4.4 บันทึกคำถามเลกเชอร์ท้ายคาบ (Handwritten Q&A h1.1 & h1.2)
5. [สรุปคีย์เวิร์ดและสูตรท่องจำสำหรับสอบ (Quick Memorization Matrix)](#สรุปคีย์เวิร์ดและสูตรท่องจำสำหรับสอบ)

---

# บทที่ 1: Introduction to Software Engineering

### 1.1 นิยามและพื้นฐานวิศวกรรมซอฟต์แวร์
* **ซอฟต์แวร์ (Software):** ไม่ใช่แค่โค้ดหรือโปรแกรม แต่คือ **"โปรแกรมคอมพิวเตอร์และเอกสารที่เกี่ยวข้องทั้งหมด"** (Computer programs and associated documentation) เช่น เอกสารข้อกำหนด (Requirements), แบบจำลองการออกแบบ (Design models), และคู่มือการใช้งาน (User documentation)
* **วิศวกรรมซอฟต์แวร์ (Software Engineering - SE):** คือ **สาขาวิชาวิศวกรรมที่เกี่ยวข้องกับทุกแง่มุมของการผลิตซอฟต์แวร์** (An engineering discipline that is concerned with all aspects of software production) ตั้งแต่ขั้นตอนแรกของการกำหนดความต้องการ (Specification) ไปจนถึงการบำรุงรักษาและวิวัฒนาการระบบหลังเปิดใช้งาน (Evolution)
* **ทำไม SE ถึงสำคัญ?**
  1. เศรษฐกิจของประเทศที่พัฒนาแล้วทั้งหมดต้องพึ่งพาซอฟต์แวร์
  2. ในระยะยาว การใช้วิธีการทางวิศวกรรมซอฟต์แวร์ **ถูกกว่าและคุ้มค่ากว่า** การเขียนโปรแกรมแบบโปรเจกต์ส่วนตัว

---

### 1.2 4 คุณลักษณะสำคัญของซอฟต์แวร์ที่ดี (4 Essential Attributes of Good Software)
อาจารย์เน้นย้ำว่าเป็นหัวใจของซอฟต์แวร์คุณภาพระดับมืออาชีพ:

| คุณลักษณะ (Attribute) | นิยามภาษาอังกฤษ (Sommerville) | คำอธิบายภาษาไทยและตัวอย่าง |
| :--- | :--- | :--- |
| **1. Maintainability**<br>*(ความสามารถในการบำรุงรักษา)* | Software should be written in such a way that it can evolve to meet the changing needs of customers. | ซอฟต์แวร์ต้องเขียนและจัดโครงสร้างให้อ่านง่าย แก้ไขง่าย และรองรับการเปลี่ยนแปลงของธุรกิจในอนาคตได้ดี |
| **2. Dependability & Security**<br>*(ความเชื่อถือได้และความปลอดภัย)* | Includes reliability, security and safety. Software should not cause physical or economic damage in system failure. | ระบบต้องมีความเสถียร ไม่พังง่าย ป้องกันการเจาะระบบได้ และหากเกิดข้อผิดพลาดต้องไม่สร้างความเสียหายต่อชีวิตหรือทรัพย์สิน |
| **3. Efficiency**<br>*(ประสิทธิภาพการใช้ทรัพยากร)* | Software should not make wasteful use of system resources such as memory and processor cycles. | ไม่กินทรัพยากรเครื่องโดยไม่จำเป็น (RAM, CPU, Bandwidth) และมี Response Time ที่รวดเร็วทันใจ |
| **4. Acceptability**<br>*(การยอมรับจากผู้ใช้งาน)* | Software must be acceptable to the type of users for which it is designed (understandable, usable, compatible). | ผู้ใช้งานยอมรับ เข้าใจง่าย ใช้งานสะดวก ไม่ซับซ้อน และเข้ากันได้กับระบบอื่นที่ผู้ใช้มีอยู่ |

---

### 1.3 ความแตกต่างระหว่าง CS vs SE vs System Engineering
* **Computer Science (CS):** เน้นที่ **ทฤษฎีและพื้นฐานทางคอมพิวเตอร์** (Theories & Fundamentals) เช่น อัลกอริทึม โครงสร้างข้อมูล ทฤษฎีการคำนวณ
* **Software Engineering (SE):** เน้นที่ **การนำมาปฏิบัติจริงเพื่อสร้างและส่งมอบซอฟต์แวร์ที่มีประโยชน์** (Practicalities of developing and delivering useful software) ภายใต้ข้อจำกัดด้านงบประมาณและเวลา
* **System Engineering:** ครอบคลุมภาพรวมของ **ระบบคอมพิวเตอร์ทั้งหมด** ทั้ง Hardware, Software, และ Process Engineering โดยที่ **SE เป็นส่วนย่อยหนึ่งของ System Engineering**

---

### 1.4 4 กิจกรรมพื้นฐานของกระบวนการพัฒนา (4 Fundamental Process Activities)
ไม่ว่าจะใช้โมเดลการพัฒนาแบบใด (Waterfall, Agile, หรือ Reuse) ทุกกระบวนการจะต้องประกอบด้วย 4 กิจกรรมนี้เสมอ:
1. **Software Specification:** ลูกค้าและวิศวกรกำหนดร่วมกันว่าซอฟต์แวร์ต้องทำอะไรได้บ้างและมีข้อจำกัดอย่างไร
2. **Software Development:** ขั้นตอนการออกแบบสถาปัตยกรรม (Design) และการเขียนโค้ดโปรแกรม (Programming)
3. **Software Validation:** การตรวจรับรองและทดสอบระบบ (Testing) เพื่อให้มั่นใจว่าเป็นสิ่งที่ลูกค้าต้องการจริง
4. **Software Evolution:** การปรับปรุง แก้ไข และพัฒนาซอฟต์แวร์เพิ่มเติมเพื่อรองรับความต้องการและสภาพแวดล้อมที่เปลี่ยนไป

---

### 1.5 โครงสร้างต้นทุนของซอฟต์แวร์ (Software Engineering Costs)
* **สัดส่วนต้นทุนการพัฒนา:** 
  * ประมาณ **60% เป็นต้นทุนการพัฒนา (Development costs)**
  * ประมาณ **40% เป็นต้นทุนการทดสอบระบบ (Testing costs)**
* **Custom Software Evolution:** สำหรับซอฟต์แวร์ที่สร้างเฉพาะงาน ต้นทุนในการปรับปรุงบำรุงรักษา (Evolution/Maintenance) ตลอดอายุการใช้งาน มักจะ **สูงกว่าต้นทุนการพัฒนาแรกเริ่มหลายเท่าตัว**

---

### 1.6 ประเภทของผลิตภัณฑ์ซอฟต์แวร์ (Generic vs Customized Products)

| มิติเปรียบเทียบ | Generic Products (ซอฟต์แวร์ตลาดทั่วไป) | Customized Products (ซอฟต์แวร์สั่งทำเฉพาะ) |
| :--- | :--- | :--- |
| **นิยาม** | ซอฟต์แวร์ Stand-alone ที่ผลิตขึ้นเพื่อวางขายในท้องตลาดให้ใครก็ได้ที่ต้องการซื้อ | ซอฟต์แวร์ที่ถูกว่าจ้างและพัฒนาขึ้นเพื่อตอบสนองความต้องการของลูกค้าเฉพาะราย |
| **เจ้าของ Specification** | **ผู้พัฒนาซอฟต์แวร์ (Software Developer)** เป็นผู้ตัดสินใจว่าจะเพิ่ม/ลดฟีเจอร์ใด | **ลูกค้า (Customer)** เป็นเจ้าของข้อกำหนดและเป็นผู้สั่งให้ปรับเปลี่ยนตามต้องการ |
| **ตัวอย่าง** | MS Windows, Adobe Photoshop, AutoCAD, App สำเร็จรูป | ระบบควบคุมการบิน, ระบบเวชระเบียนโรงพยาบาลเฉพาะทาง, ระบบควบคุมรถไฟ |

---

### 1.7 ประเภทของแอปพลิเคชัน (8 Application Types)
1. **Stand-alone Applications:** โปรแกรมที่รันบนคอมพิวเตอร์ส่วนบุคคล (PC) โดยไม่ต้องต่อเน็ต เช่น โปรแกรมแต่งภาพ, โปรแกรมบัญชีออฟไลน์
2. **Interactive Transaction-Based Applications:** แอปที่รันบน Server ระยะไกล ผู้ใช้เข้าถึงผ่าน Web หรือมือถือ เช่น E-commerce, ระบบจองตั๋ว
3. **Embedded Control Systems:** ระบบสมองกลฝังตัวควบคุมอุปกรณ์ฮาร์ดแวร์ (มีจำนวนมากที่สุดในโลก) เช่น ปั๊มฉีดอินซูลิน, ระบบเบรก ABS
4. **Batch Processing Systems:** ระบบประมวลผลข้อมูลชุดใหญ่เป็นรอบๆ ตามเวลา เช่น ระบบคำนวณเงินเดือนสิ้นเดือน, ระบบพิมพ์ใบแจ้งหนี้
5. **Entertainment Systems:** ระบบเพื่อความบันเทิงส่วนบุคคล เช่น วิดีโอเกม
6. **Systems for Modeling and Simulation:** ระบบจำลองสถานการณ์ทางวิทยาศาสตร์และวิศวกรรม เช่น ระบบพยากรณ์อากาศ, แบบจำลองการบิน
7. **Data Collection Systems:** ระบบรวบรวมข้อมูลจากสิ่งแวดล้อมผ่านเซนเซอร์ เช่น สถานีตรวจวัดสภาพอากาศทุรกันดาร
8. **Systems of Systems:** ระบบขนาดใหญ่ที่ประกอบขึ้นจากการทำงานร่วมกันของซอฟต์แวร์หลายๆ ระบบ

---

### 1.8 วิศวกรรมซอฟต์แวร์บนอินเทอร์เน็ตและเว็บ (Internet & Web-Based SE)
* เว็บได้เปลี่ยนโฉมวิศวกรรมซอฟต์แวร์:
  * **Software Reuse:** เป็นแนวทางหลักในการสร้างระบบเว็บ โดยนำคอมโพเนนต์และไลบรารีที่มีอยู่แล้วมาประกอบเข้าด้วยกัน
  * **Incremental & Agile Development:** ระบบเว็บไม่สามารถกำหนด Requirement ล่วงหน้าได้ทั้งหมด จึงต้องใช้วิธีทยอยพัฒนาและปล่อยใช้งานทีละส่วน
  * **Service-Oriented Systems (SOA):** พัฒนาระบบด้วย Stand-alone Web Services ที่เชื่อมต่อกันผ่าน API
  * **Rich Interfaces:** เทคโนโลยีเช่น AJAX, HTML5, และ Framework สมัยใหม่ช่วยสร้างหน้าจอที่ตอบสนองรวดเร็วในเบราว์เซอร์

---

### 1.9 จรรยาบรรณวิชาชีพและประเด็นความรับผิดชอบ (Professional Responsibility)
วิศวกรซอฟต์แวร์ต้องมีพฤติกรรมที่ซื่อสัตย์และมีความรับผิดชอบทางจริยธรรม 4 ประเด็นสำคัญ:
1. **Confidentiality (การรักษาความลับ):** ต้องรักษาความลับของนายจ้างและลูกค้าเสมอ แม้จะไม่ได้เซ็นสัญญา NDA ก็ตาม
2. **Competence (ความรู้ความสามารถ):** ต้องไม่แอบอ้างความสามารถเกินจริง และต้องไม่รับงานที่ตนเองรู้ว่าไม่มีความสามารถเพียงพอ
3. **Intellectual Property Rights (ทรัพย์สินทางปัญญา):** ต้องเคารพกฎหมายสิทธิบัตรและลิขสิทธิ์ ไม่นำโค้ดหรือทรัพย์สินของผู้อื่นมาใช้โดยมิชอบ
4. **Computer Misuse (การไม่ใช้คอมพิวเตอร์ในทางที่ผิด):** ต้องไม่ใช้ทักษะทางเทคนิคไปโจมตี ทำลายข้อมูล หรือปล่อยไวรัสใส่เครื่องของผู้อื่น

---

### 1.10 จรรยาบรรณวิศวกรซอฟต์แวร์ 8 ประการ (ACM/IEEE Code of Ethics)
สมาคมวิชาชีพ ACM/IEEE กำหนดหลักการ 8 ข้อ เพื่อเป็นแนวทางตัดสินใจเชิงจริยธรรม:
1. **PUBLIC (สาธารณะ):** ปฏิบัติงานโดยคำนึงถึงผลประโยชน์และความปลอดภัยของสาธารณชนเป็นสำคัญที่สุด
2. **CLIENT AND EMPLOYER (ลูกค้าและนายจ้าง):** ทำงานเพื่อประโยชน์สูงสุดของลูกค้าและนายจ้าง โดยต้องไม่ขัดต่อผลประโยชน์สาธารณะ
3. **PRODUCT (ผลิตภัณฑ์):** มั่นใจว่าผลงานและซอฟต์แวร์ที่ส่งมอบมีคุณภาพและมาตรฐานวิชาชีพสูงสุดเท่าที่จะทำได้
4. **JUDGMENT (ดุลยพินิจ):** รักษาความซื่อสัตย์สุจริตและความเป็นอิสระในการตัดสินใจทางวิชาชีพ
5. **MANAGEMENT (การบริหารจัดการ):** ผู้บริหารต้องส่งเสริมและสนับสนุนกระบวนการพัฒนาที่มีจริยธรรม
6. **PROFESSION (วิชาชีพ):** ส่งเสริมและรักษาเกียรติภูมิ ชื่อเสียง และความน่าเชื่อถือของวิชาชีพวิศวกรซอฟต์แวร์
7. **COLLEAGUES (เพื่อนร่วมงาน):** ปฏิบัติต่อเพื่อนร่วมงานอย่างเป็นธรรม เกื้อกูล และให้เกียรติซึ่งกันและกัน
8. **SELF (การพัฒนาตนเอง):** มุ่งมั่นเรียนรู้และพัฒนาทักษะวิชาชีพตลอดชีวิต (Lifelong learning)

---

### 1.11 4 กรณีศึกษาประจำวิชา (4 Standard Case Studies)
1. **Personal Insulin Pump System:** ระบบสมองกลฝังตัวทางการแพทย์ (Safety-critical embedded system) ทำหน้าที่ตรวจวัดระดับน้ำตาลในเลือดและสั่งฉีดยาอินซูลินอัตโนมัติ ข้อผิดพลาดอาจทำให้คนไข้เสียชีวิตได้
2. **Mentcare System:** ระบบเวชระเบียนข้อมูลผู้ป่วยสุขภาพจิตสำหรับคลินิกชุมชน (Patient Information System) จุดเด่นคือรองรับการทำงานแบบออฟไลน์เมื่อเน็ตหลุด และมีระบบเตือนภัยผู้ป่วยกลุ่มเสี่ยง
3. **Wilderness Weather Station:** ระบบเก็บข้อมูลสภาพอากาศในพื้นที่ป่าทุรกันดารผ่านชุดเซนเซอร์ (Data Collection System) ควบคุมพลังงานแบตเตอรี่และสื่อสารผ่านดาวเทียม
4. **iLearn Digital Learning Environment:** ระบบการเรียนรู้ออนไลน์สำหรับโรงเรียนที่สร้างบนสถาปัตยกรรม Service-Oriented รวมแอปและบริการต่างๆ เช่น Wiki, Photo Sharing, VLE

---

# บทที่ 2: Software Processes

### 2.1 นิยามของ Software Process และองค์ประกอบ
* **Software Process:** ชุดของกิจกรรมที่มีโครงสร้างชัดเจนเพื่อใช้ในการพัฒนา ผลิต และบำรุงรักษาซอฟต์แวร์
* **องค์ประกอบในการอธิบายกระบวนการ (Process Description Components):**
  * **Products (ผลผลิต):** ผลลัพธ์ที่ได้จากกิจกรรม เช่น เอกสาร Specification, Source Code, Test Suite
  * **Roles (บทบาท):** หน้าที่ความรับผิดชอบของบุคคลที่เกี่ยวข้อง เช่น Project Manager, Software Architect, Tester
  * **Pre-conditions & Post-conditions:** เงื่อนไขที่ต้องเป็นจริงก่อนเริ่มกิจกรรม และเงื่อนไขที่จะเป็นจริงหลังสิ้นสุดกิจกรรม

---

### 2.2 Plan-Driven vs Agile Processes
* **Plan-Driven Processes:** กิจกรรมทั้งหมดถูกวางแผนไว้ล่วงหน้าอย่างละเอียด และวัดความก้าวหน้าเทียบกับแผนงานที่ตั้งไว้ (เช่น Waterfall)
* **Agile Processes:** การวางแผนทำแบบค่อยเป็นค่อยไป (Incremental) เน้นความยืดหยุ่นและการปรับเปลี่ยนตามความต้องการของลูกค้าได้รวดเร็ว
* *หมายเหตุ:* ในทางปฏิบัติ ซอฟต์แวร์ขนาดใหญ่มักผสมผสานทั้ง Plan-driven และ Agile เข้าด้วยกัน

---

### 2.3 ตารางเปรียบเทียบ 3 โมเดลการพัฒนาซอฟต์แวร์หลัก

| มิติเปรียบเทียบ | 1. Waterfall Model | 2. Incremental Development Model | 3. Reuse-oriented (Integration & Config) |
| :--- | :--- | :--- | :--- |
| **แนวคิดหลัก** | ทำงานเป็นขั้นตอนตามลำดับ (Sequential) แต่ละเฟสต้องเสร็จ 100% ก่อนเริ่มเฟสถัดไป | แบ่งระบบออกเป็นส่วนย่อยๆ (Increments) ทยอยพัฒนา ส่งมอบ และประเมินผลทีละเวอร์ชัน | นำซอฟต์แวร์สำเร็จรูป (COTS) หรือ Web Services ที่มีอยู่แล้วมาปรับแต่งและเชื่อมต่อเข้าด้วยกัน |
| **5 ขั้นตอนหลัก** | 1. Requirements Definition<br>2. System & SW Design<br>3. Implementation & Unit Test<br>4. Integration & System Test<br>5. Operation & Maintenance | 1. Outline Description<br>2. Concurrent Activities (Spec, Dev, Validation)<br>3. Initial Version<br>4. Intermediate Versions<br>5. Final Version | 1. Requirements Specification<br>2. Software Discovery & Evaluation<br>3. Requirements Refinement<br>4. Application System Config<br>5. Component Adaptation & Integration |
| **ข้อดี (Pros)** | • มีโครงสร้างชัดเจน เข้าใจง่าย<br>• วางแผนระยะเวลาและงบประมาณได้ง่ายตั้งแต่แรกเริ่ม<br>• มีเอกสารประกอบครบถ้วน | • รองรับการเปลี่ยน Requirement ได้ดี<br>• ลดต้นทุนการแก้ไขงาน (Rework cost)<br>• ลูกค้าได้เห็นและใช้งานระบบจริงได้รวดเร็ว | • ลดต้นทุนและลดความเสี่ยงอย่างมาก<br>• นำระบบออกสู่ตลาดได้เร็ว (Fast time-to-market)<br>• ใช้โค้ดที่ผ่านการทดสอบมาแล้ว |
| **ข้อเสีย (Cons)** | • แก้ไข Requirement ระหว่างทางได้ยากมากและมีค่าใช้จ่ายสูง<br>• ลูกค้าเห็นผลงานจริงเมื่อสิ้นสุดโครงการเท่านั้น | • ผู้บริหารติดตามความคืบหน้ายาก (Process is not visible)<br>• โครงสร้างระบบ (Architecture) อาจเสื่อมลงหากไม่ Refactor | • ต้องยอมประนีประนอม Requirement ตามฟังก์ชันของ COTS<br>• ขาดอำนาจควบคุมการอัปเดตของ Third-party |
| **ความเหมาะสม** | • ระบบความปลอดภัยวิกฤต (Safety-critical)<br>• โครงการขนาดใหญ่ที่แบ่งงานหลายไซต์/หลายทีม<br>• Requirement นิ่งและชัดเจน | • ระบบธุรกิจทั่วไปและ Startup<br>• Web และ Mobile Application<br>• ระบบที่ต้องการ Feedback จากผู้ใช้ต่อเนื่อง | • ระบบมาตรฐานทั่วไปในองค์กร เช่น ERP, CRM, HR<br>• ระบบ E-commerce สำเร็จรูป |

---

### 2.4 กิจกรรมการออกแบบระบบ (Design Process Activities)
เมื่อได้ Requirement แล้ว ขั้นตอนการออกแบบซอฟต์แวร์ประกอบด้วย 4 กิจกรรมหลัก:
1. **Architectural Design:** กำหนดโครงสร้างภาพรวมของระบบ โมดูลหลัก ความสัมพันธ์ และการกระจายตัวของระบบ
2. **Database Design:** ออกแบบโครงสร้างข้อมูลและ Entity-Relationship ที่จะจัดเก็บในฐานข้อมูล
3. **Interface Design:** กำหนดรูปแบบการเชื่อมต่อสื่อสารระหว่างคอมโพเนนต์และ API
4. **Component Selection & Design:** ค้นหาคอมโพเนนต์ที่นำกลับมาใช้ใหม่ได้ หากไม่มีจึงออกแบบเพื่อเขียนขึ้นมาใหม่

---

### 2.5 ลำดับขั้นการทดสอบระบบ & Testing V-Model

```
Requirements Specification ──────[ Acceptance Test Plan ]──────> Acceptance Testing
       │                                                                ▲
System Specification ─────────[ System Integration Plan ]─────> System Integration Test
       │                                                                ▲
System Design ──────────────[ Sub-system Integration Plan ]───> Sub-system Integration Test
       │                                                                ▲
Detailed Design ────────────[ Module / Unit Test Plan ]───────> Module & Unit Testing
       │                                                                ▲
       └───────────────────> Implementation (Coding) ───────────────────┘
```

* **1. Component Testing (Unit Testing):** โปรแกรมเมอร์ทดสอบฟังก์ชัน ออบเจกต์ หรือโมดูลย่อยแต่ละตัวอย่างเป็นอิสระ
* **2. System Testing:** นำโมดูลทั้งหมดมาประกอบรวมกันเพื่อทดสอบระบบทั้งระบบ โดยเน้นตรวจหา Emergent Properties
* **3. Customer / Acceptance Testing:** ทดสอบระบบด้วยข้อมูลจริงของลูกค้า เพื่อตรวจรับมอบงานว่าตรงตามสัญญาและตอบโจทย์ธุรกิจ

---

### 2.6 วิวัฒนาการของซอฟต์แวร์ (Software Evolution)
* **วงจร System Evolution 4 ขั้นตอน:**
  1. `Define System Requirements` (กำหนดความต้องการใหม่ที่เปลี่ยนไป)
  2. `Assess Existing Systems` (ประเมินขีดความสามารถของระบบเดิม)
  3. `Propose System Changes` (เสนอแนวทางแก้ไขและปรับปรุง)
  4. `Modify Systems` (ดำเนินการแก้ไขระบบจนได้ New System)

---

### 2.7 การรับมือกับการเปลี่ยนแปลง (Coping with Change)
* **Change Anticipation (การคาดการณ์การเปลี่ยนแปลง):** นำกิจกรรมที่ช่วยมองเห็น Requirement ล่วงหน้ามาใช้ เช่น การสร้าง **System Prototype**
* **Change Tolerance (การทนทานต่อการเปลี่ยนแปลง):** ออกแบบกระบวนการให้รองรับการแก้ไขได้ง่ายและต้นทุนต่ำ เช่น การทำ **Incremental Delivery**
* **Throw-away Prototyping (ตัวต้นแบบที่สร้างแล้วทิ้ง):**
  * สร้างขึ้นเพื่อสำรวจ Requirement ที่ยังไม่ชัดเจนกับลูกค้า
  * **ห้ามนำไปใช้เป็นระบบจริงเด็ดขาด** เนื่องจาก: ไม่มีเอกสารประกอบ, โครงสร้างโค้ดเสื่อมเสียจากการแก้แบบเร่งด่วน, และไม่ได้ปรับแต่งด้าน Non-functional (ความปลอดภัย/ความเร็ว)

---

### 2.8 การปรับปรุงกระบวนการและ 5 ระดับวุฒิภาวะ (SEI CMM Levels)
* **วงจร Process Improvement Cycle:** `Measure (วัดผล)` ➔ `Analyze (วิเคราะห์จุดอ่อน)` ➔ `Change (ปรับปรุงกระบวนการ)`
* **5 ระดับวุฒิภาวะตาม SEI Capability Maturity Model (CMM):**
  * **Level 1 - Initial:** ไร้แบบแผน ควบคุมไม่ได้ ขึ้นอยู่กับความสามารถเฉพาะตัวบุคคล (Ad-hoc)
  * **Level 2 - Repeatable / Managed:** มีกระบวนการบริหารจัดการโครงการพื้นฐานที่สามารถทำซ้ำได้ในโครงการที่คล้ายกัน
  * **Level 3 - Defined:** มีกระบวนการมาตรฐานที่ได้รับการบันทึกเป็นลายลักษณ์อักษรและประกาศใช้ทั่วทั้งองค์กร
  * **Level 4 - Quantitatively Managed:** มีการควบคุมและวัดผลคุณภาพของกระบวนการและผลิตภัณฑ์ด้วยตัวเลขทางสถิติ
  * **Level 5 - Optimizing:** องค์กรมีการประเมินและปรับปรุงกระบวนการพัฒนาอย่างต่อเนื่องเชิงรุก

---

# บทที่ 4: Requirements Engineering

### 4.1 นิยามและระดับการแปลงความต้องการ
* **Requirements Engineering (RE):** กระบวนการค้นหา วิเคราะห์ บันทึก และตรวจสอบความต้องการและข้อจำกัดในการทำงานของระบบ
* **ระดับ Abstraction (Davis):** ในตอนเริ่มประมูลโครงการ Requirement ต้องมีความ Abstract ยืดหยุ่นพอให้ผู้รับเหมาเสนอแนวทางได้ แต่เมื่อเซ็นสัญญาแล้ว ต้องเขียนรายละเอียดเชิงลึก (Detailed System Definition) เพื่อใช้เป็นเกณฑ์ตรวจรับงาน

---

### 4.2 User Requirements vs System Requirements
* **User Requirements:** ข้อความบรรยายระดับสูงด้วยภาษาธรรมชาติ (Natural language) และแผนภาพภาพรวม เขียนขึ้นเพื่อให้ลูกค้าและผู้ใช้งานที่ไม่มีพื้นฐานเทคนิคเข้าใจได้ง่าย
* **System Requirements:** เอกสารระบุรายละเอียดเชิงโครงสร้างและทางเทคนิคของฟังก์ชัน บริการ และข้อจำกัด เพื่อให้นักพัฒนาและสถาปนิกนำไปออกแบบและสร้างจริง

---

### 4.3 การจำแนกประเภทความต้องการ 4 ด้าน (Classification)

```
                              Requirements
                                   │
     ┌─────────────────────────────┼─────────────────────────────┐
     ▼                             ▼                             ▼
Functional Requirements    Non-Functional Requirements    Domain Requirements
(WHAT system shall do)     (HOW system performs)          (Specific business rules)
                                   │
                 ┌─────────────────┼─────────────────┐
                 ▼                 ▼                 ▼
          Product Reqs     Organisational Reqs  External Reqs
          - Usability       - Environmental      - Legislative (PDPA)
          - Performance     - Operational        - Safety/Security
          - Reliability     - Development        - Ethical
```

1. **Functional Requirements (FR - ความต้องการเชิงหน้าที่):** ระบุว่าระบบต้อง **"ทำอะไรได้บ้าง"** (What the system should do), พฤติกรรมการตอบสนองต่อ Input, และสิ่งที่ระบบ **ต้องไม่ทำ**
2. **Non-Functional Requirements (NFR - ความต้องการเชิงคุณลักษณะ):** ระบุมาตรฐาน ข้อจำกัด และประสิทธิภาพการทำงานของระบบ (How the system performs) แบ่งเป็น:
   * **Product Requirements:** Usability, Speed, Memory space, Reliability, Portability
   * **Organisational Requirements:** Operational standards, Development language/IDE
   * **External Requirements:** Legislative (PDPA/HIPAA), Accounting rules, Safety regulations
3. **Domain Requirements (ความต้องการเชิงโดเมน):** ข้อกำหนดเฉพาะทางที่เกิดจากบริบทของธุรกิจนั้นๆ โดยตรง เช่น การเชื่อมโยงกับฐานข้อมูล Active Directory ของมหาวิทยาลัย หรือการปฏิบัติตามมาตรฐานกระทรวงสาธารณสุข
4. **Constraints (ข้อจำกัดโครงการ):** ข้อจำกัดด้านงบประมาณ กรอบเวลา ภาษาหรือเฟรมเวิร์กที่ถูกบังคับใช้ เช่น ต้องเขียนด้วย Flutter, งบไม่เกิน 200,000 บาท, ต้องเสร็จใน 3 เดือน

---

### 4.4 ผังกระบวนการวิศวกรรมความต้องการ (Spiral RE Process)
กระบวนการ RE เป็นวงจรวนซ้ำ (Iterative Spiral) ประกอบด้วย 4 กิจกรรมหลัก:
1. **Requirements Discovery & Elicitation:** พูดคุยและค้นหาความต้องการจาก Stakeholder
2. **Requirements Classification & Organisation:** จัดหมวดหมู่และจัดกลุ่ม Requirement ที่สัมพันธ์กัน
3. **Requirements Prioritisation & Negotiation:** จัดลำดับความสำคัญและเจรจาไกล่เกลี่ยข้อกำหนดที่ขัดแย้งกัน
4. **Requirements Specification:** บันทึกข้อกำหนดลงในเอกสารมาตรฐานเพื่อนำไปสู่รอบถัดไป

---

### 4.5 เทคนิคการรวบรวมความต้องการ (Elicitation Techniques)
* **1. Interviewing (การสัมภาษณ์):**
  * *Closed Interviews:* คำถามปลายปิด มีชุดคำตอบจำกัด
  * *Open Interviews:* คำถามปลายเปิด สำรวจประเด็นกว้างๆ
  * *ปัญหาที่พบ:* ผู้เชี่ยวชาญใช้ศัพท์เฉพาะทาง (Domain jargon) และผู้ใช้อาจลืมบอกงานที่เป็นความเคยชิน
* **2. Ethnography (การสังเกตเชิงชาติพันธุ์วรรณา):**
  * นักวิเคราะห์เข้าไปฝังตัวสังเกตการณ์การทำงานจริงในสถานที่จริง เพื่อดู **"วิธีที่คนทำงานจริง (How people actually work)"** ไม่ใช่สิ่งที่ระเบียบการเขียนไว้
  * *ข้อจำกัด:* ไม่สามารถบอกฟังก์ชันใหม่ที่ควรเพิ่มเข้ามาในอนาคตได้ (เห็นแค่งานปัจจุบัน)
* **3. Scenarios & User Stories:**
  * การจำลองเรื่องราวจริงทีละขั้นตอน โดย Scenario ที่ดีต้องมี 5 องค์ประกอบ:
    1) *Starting situation* (สถานะเริ่มต้น)
    2) *Normal flow of events* (ลำดับขั้นตอนปกติ)
    3) *What can go wrong* (กรณีเกิดข้อผิดพลาด/ข้อยกเว้น)
    4) *Concurrent activities* (กิจกรรมอื่นที่เกิดคู่ขนาน)
    5) *State when finished* (สถานะเมื่อสิ้นสุด)

---

### 4.6 รูปแบบการเขียนเอกสาร Requirements Specification
* **1. Natural Language:** ใช้ประโยคภาษาคน โดยมีข้อตกลง: คำว่า `shall` สำหรับข้อบังคับ (Mandatory) และ `should` สำหรับข้อแนะนำ (Desirable)
* **2. Structured Natural Language (Form-Based):** เขียนลงแบบฟอร์มมาตรฐาน มีช่องระบุ:
  * `Function`, `Description`, `Inputs`, `Source`, `Outputs`, `Destination`, `Action`, `Pre-condition`, `Post-condition`, `Side effects`
* **3. Tabular Specification:** ตารางจับคู่ **Condition ➔ Action** เหมาะกับระบบที่มีเงื่อนไขการตัดสินใจซับซ้อน เช่น การคำนวณขนาดยาอินซูลิน
* **4. Graphical Notations:** แผนภาพ UML เช่น Use Case Diagram และ Sequence Diagram

---

### 4.7 การตรวจสอบความถูกต้อง (Requirements Validation - V-C-C-R-V)
ก่อนเริ่มพัฒนาระบบ ต้องตรวจสอบเอกสารข้อกำหนดด้วยเกณฑ์ 5 ประการ:
1. **Validity (ความสมเหตุสมผล):** ฟังก์ชันตรงกับสิ่งที่ลูกค้าต้องการใช้งานจริงในการทำงานหรือไม่?
2. **Consistency (ความสอดคล้องกัน):** ข้อกำหนดต่างๆ ไม่มีความขัดแย้งหรือขัดขากันเองในเอกสาร
3. **Completeness (ความสมบูรณ์ครบถ้วน):** ระบุฟังก์ชัน ข้อจำกัด และกรณีเกิด Error ครบทุกกรณี
4. **Realism (ความเป็นไปได้จริง):** สามารถพัฒนาได้จริงภายใต้งบประมาณ เทคโนโลยี และเวลาที่มีอยู่
5. **Verifiability (ความสามารถในการทดสอบได้):** สามารถเขียนชุดทดสอบ (Test Case) เพื่อวัดผลได้อย่างเป็นรูปธรรม

---

### 4.8 กระบวนการจัดการการเปลี่ยนแปลง (Requirements Change Management)
มี 3 ขั้นตอนหลักตามลำดับ:
1. **Problem Analysis & Change Specification:** วิเคราะห์คำขอเปลี่ยนแปลงว่ามีเหตุผลสมควรหรือไม่ และร่างรายละเอียดการแก้ไข
2. **Change Analysis & Costing:** ประเมินผลกระทบต่อสถาปัตยกรรม งบประมาณ และเวลาส่งมอบ โดยอาศัยความสัมพันธ์แบบ Traceability
3. **Change Implementation:** ดำเนินการแก้ไขเอกสาร Requirements, งานออกแบบ, ซอร์สโค้ด และชุดทดสอบให้สอดคล้องกัน

---

# คลังเฉลยการบ้านและบันทึกข้อสอบ

### 4.1 เฉลยการบ้าน 1: PizzaFriend Requirements
* **Functional Requirements:**
  * ระบบต้องอนุญาตให้ลูกค้าลงทะเบียนและ Login ด้วย email และรหัสผ่านได้
  * ระบบต้องแสดงเมนูพิซซ่าทั้งหมด พร้อมรูปภาพ ชื่อสินค้า และราคาอย่างชัดเจน
  * ลูกค้าต้องสามารถเลือกขนาดพิซซ่า ชนิดแป้ง และ Toppings ตามที่ต้องการได้
  * ลูกค้าต้องสามารถเพิ่ม แก้ไข และลบรายการพิซซ่าใน Shopping Cart ได้
  * ระบบต้องคำนวณราคารวมและแสดง Order Summary ก่อนยืนยันคำสั่งซื้อ
  * ระบบต้องรองรับการชำระเงินผ่าน Mobile Banking และ Credit Card
  * เมื่อชำระเงินสำเร็จ ระบบต้องส่งใบเสร็จและ Order Confirmation ไปยัง email ของลูกค้าทันที
* **Non-Functional Requirements:**
  * *Usability:* แอปต้องใช้งานง่าย ลูกค้าใหม่สั่งพิซซ่าครั้งแรกได้เสร็จภายในเวลาไม่เกิน 5 นาที
  * *Performance:* ระบบตอบสนองต่อการคลิกเลือกเมนูภายในเวลาไม่เกิน 2 วินาที
  * *Capacity:* รองรับผู้ใช้งานพร้อมกันอย่างน้อย 300 คน โดยไม่ช้าหรือหยุดทำงาน
  * *Security:* ข้อมูลทางการเงินต้องถูกเข้ารหัสทุกครั้งที่มีการทำธุรกรรมผ่านแอป
* **Domain Application:**
  * ระบบต้องสร้าง Daily Sales Report เพื่อให้เจ้าของร้านตรวจสอบยอดขายประจำวัน
  * ระบบต้องสร้างรายงานเมนูพิซซ่า ขนาด แป้ง และ Toppings ยอดนิยมเพื่อวางแผนสต็อกและโปรโมชัน
  * ระบบต้องจัดเก็บและประมวลผลข้อมูลส่วนบุคคลของลูกค้าให้เป็นไปตามกฎหมาย PDPA
* **Constraints:**
  * ทีมพัฒนาต้องใช้ Flutter Framework ในการพัฒนาแอปพลิเคชัน
  * แอปต้องรองรับทั้ง Android และ iOS ด้วย Source Code ชุดเดียวกัน
  * แอปต้องพัฒนา ทดสอบ และพร้อมเปิดให้บริการภายในเวลาไม่เกิน 3 เดือน

---

### 4.2 เฉลยการบ้าน 2: EasyClinic 9 Stakeholders & Roles

| # | Stakeholder (ผู้มีส่วนได้ส่วนเสีย) | บทบาทหน้าที่ในระบบ (Role & Responsibility) |
| :-: | :--- | :--- |
| 1 | **เจ้าของคลินิก (Clinic Owner / Sponsor)** | เป็นเจ้าของโครงการ กำหนดเป้าหมาย งบประมาณ ระยะเวลา และ Business Requirements รวมถึงตรวจ Daily Report |
| 2 | **ผู้ป่วย (Patient / End User)** | ลงทะเบียนด้วยเบอร์โทร/บัตรประชาชน เลือกแผนกและแพทย์ จองวันเวลา จัดการนัดหมาย และรับ Reminder |
| 3 | **แพทย์ (Doctor)** | ใช้ Dashboard เพื่อตรวจสอบและจัดการตารางนัดหมายของตนเอง รวมถึงปรับเปลี่ยนเวลาตรวจเมื่อจำเป็น |
| 4 | **เจ้าหน้าที่คลินิก (Clinic Staff)** | ตรวจสอบรายการจอง อัปเดตสถานะผู้ป่วย ("มาถึงแล้ว" / "ไม่มาตามนัด") และจัดการการเลื่อนคิวเร่งด่วน |
| 5 | **ผู้จัดการคลินิก (Clinic Manager)** | ตรวจสอบรายงานการให้บริการประจำวันและสถิติผู้ป่วยแยกตามแผนกเพื่อวางแผนบุคลากร |
| 6 | **ผู้ดูแลระบบ (System Administrator)** | จัดการบัญชีผู้ใช้และ Access Control ดูแล Server สำรองข้อมูล ตรวจสอบความปลอดภัยและแก้ปัญหาเทคนิค |
| 7 | **ทีมพัฒนาซอฟต์แวร์ (Developers / UX/UI)** | วิเคราะห์ Requirements ออกแบบ พัฒนา ทดสอบระบบให้รองรับ Web, iOS, Android โดยคำนึงถึงผู้สูงอายุ |
| 8 | **ผู้ให้บริการ SMS & Email (3rd Party Gateway)** | ให้บริการส่งข้อความยืนยันและ Reminder เตือนก่อนเวลานัด 1 วัน และ 1 ชั่วโมง ผ่าน API |
| 9 | **หน่วยงานกำกับดูแล (Regulators / PDPA / สธ.)** | กำหนดและตรวจสอบแนวทางการคุ้มครองข้อมูลสุขภาพผู้ป่วยตามกฎหมาย PDPA และแนวทางกระทรวงสาธารณสุข |

---

### 4.3 การบ้านการสะท้อนจริยธรรม 4 ด้าน ("ฉันจะ...")
* **1. ด้านความรับผิดชอบต่อส่วนรวม (Public Interest):** ฉันจะพัฒนาซอฟต์แวร์ที่คำนึงถึงความปลอดภัย ความเป็นส่วนตัว และไม่สร้างระบบที่ส่งผลกระทบหรือสร้างความเสียหายต่อสังคม
* **2. ด้านความลับและความซื่อสัตย์ต่อลูกค้า/องค์กร (Confidentiality & Loyalty):** ฉันจะไม่เปิดเผยข้อมูลที่เป็นความลับของลูกค้าหรือบริษัท และไม่นำโค้ดหรือข้อมูลภายในไปแสวงหาประโยชน์ส่วนตน
* **3. ด้านคุณภาพและมาตรฐานวิชาชีพ (Product Quality & Competence):** ฉันจะส่งมอบโค้ดที่มีคุณภาพ มีการทดสอบอย่างถูกต้องตามมาตรฐาน และไม่ปล่อยผ่านช่องโหว่หรือบั๊กที่อาจก่อให้เกิดอันตราย
* **4. ด้านความซื่อสัตย์และการยอมรับข้อจำกัด (Integrity & Limitations):** ฉันจะตรงไปตรงมา ไม่รับงานที่เกินความสามารถหรือมีผลประโยชน์ทับซ้อน และยอมรับความผิดพลาดเพื่อนำไปแก้ไขโดยไม่ปกปิด

---

### 4.4 บันทึกคำถามเลกเชอร์ท้ายคาบ (Handwritten Q&A)
* **Q1: What are the key challenges facing software engineering?**
  * *คำตอบ:* ปัจจุบันซอฟต์แวร์มีความหลากหลายเพิ่มขึ้น (Increasing diversity), ต้องลดระยะเวลาส่งมอบงาน (Reduced delivery times), และต้องพัฒนาซอฟต์แวร์ที่เชื่อถือได้ (Developing trustworthy software)
* **Q2: What are the costs of software engineering?**
  * *คำตอบ:* แบ่งเป็น 2 ส่วนหลัก คือ ต้นทุนการพัฒนา 60% และต้นทุนการทดสอบระบบ 40% และสำหรับซอฟต์แวร์สั่งทำเฉพาะ ต้นทุนการปรับปรุงแก้ไข (Evolution) มักสูงกว่าต้นทุนการพัฒนาแรกเริ่ม
* **Q3: What are the best software engineering techniques and methods?**
  * *คำตอบ:* ไม่มีวิธีใดดีที่สุดสำหรับทุกงาน ขึ้นอยู่กับประเภทของระบบ เช่น เกมควรสร้างแบบ Prototype ส่วนระบบความปลอดภัยวิกฤตต้องมี Specification ที่สมบูรณ์และวิเคราะห์ได้
* **Q4: What differences has the web made to software engineering?**
  * *คำตอบ:* ทำให้เกิดบริการซอฟต์แวร์รูปแบบใหม่ (Cloud/SaaS), เพิ่มความเป็นไปได้ในการพัฒนาระบบกระจายตัวสูง, และนำไปสู่ความก้าวหน้าด้านภาษาโปรแกรมและการนำซอฟต์แวร์กลับมาใช้ใหม่ (Reuse)

---

# สรุปคีย์เวิร์ดและสูตรท่องจำสำหรับสอบ

| หัวข้อสำคัญ | คีย์เวิร์ดท่องจำ (Mnemonics & Core Terms) |
| :--- | :--- |
| **4 Attributes of Good Software** | **M-D-E-A:** `Maintainability`, `Dependability & Security`, `Efficiency`, `Acceptability` |
| **4 Fundamental Process Activities** | **S-D-V-E:** `Specification`, `Development`, `Validation`, `Evolution` |
| **3 Software Process Models** | **Waterfall** (Sequential/Plan-driven), **Incremental** (Interleaved/Agile), **Reuse-oriented** (COTS/Integration) |
| **3 Testing Stages** | `Component Testing` (Unit) ➔ `System Testing` (Integration) ➔ `Acceptance Testing` (Customer) |
| **5 CMM Maturity Levels** | **I-R-D-Q-O:** `Initial (1)` ➔ `Repeatable/Managed (2)` ➔ `Defined (3)` ➔ `Quantitatively Managed (4)` ➔ `Optimizing (5)` |
| **5 Requirements Validation Checks** | **V-C-C-R-V:** `Validity`, `Consistency`, `Completeness`, `Realism`, `Verifiability` |
| **3 Requirements Change Stages** | `Problem Analysis & Spec` ➔ `Change Analysis & Costing` ➔ `Change Implementation` |
| **8 ACM/IEEE Ethics Principles** | `Public`, `Client & Employer`, `Product`, `Judgment`, `Management`, `Profession`, `Colleagues`, `Self` |

---
*จัดทำขึ้นเป็นพิเศษเพื่อการเตรียมสอบ Midterm วิชา Software Engineering — ขอให้ทำข้อสอบได้อย่างมั่นใจและได้คะแนน A ทุกคนครับ! 💯*
