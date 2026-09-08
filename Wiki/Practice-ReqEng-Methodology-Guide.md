# 🧭 Practice-ReqEng Master Guide: คัมภีร์หลักการอ่านโจทย์ & สูตรเขียนคำตอบข้อสอบ SE (ฉบับปี 68)
> **วัตถุประสงค์:** คู่มือนี้สรุป **ตรรกะ, กฎเกณฑ์ และสูตรสำเร็จรูปในการทำข้อสอบวิศวกรรมความต้องการ (Requirements Engineering)** อ้างอิงตามแม่แบบ `Practice-ReqEng.pdf` เพื่อให้สามารถนำไปแก้โจทย์ข้อสอบได้ทุกรูปแบบ ไม่ว่าโจทย์จะเปลี่ยนเคสไปเป็นระบบใดก็ตาม

---

## 📑 สารบัญเนื้อหา (Table of Contents)
1. [โมเดลการทำข้อสอบ 3 ขั้นตอน (The 3-Step Exam Solving Engine)](#1-โมเดลการทำข้อสอบ-3-ขั้นตอน-the-3-step-exam-solving-engine)
2. [ตาราง Keyword Hunting Matrix 4 ถังความคิด (FR / NFR / Domain / Constraints)](#2-ตาราง-keyword-hunting-matrix-4-ถังความคิด)
3. [สูตรสำเร็จรูปในการเขียนประโยคคำตอบ (Answering Formulas)](#3-สูตรสำเร็จรูปในการเขียนประโยคคำตอบ-answering-formulas)
   - 3.1 สูตร Functional Requirements (FR)
   - 3.2 สูตร Non-Functional Requirements (Usability, Performance, Capacity, Security)
   - 3.3 สูตร Domain Requirements
   - 3.4 สูตร Constraints
4. [สูตรผ่า 2 ซีก: การวิเคราะห์ Stakeholders & Roles](#4-สูตรผ่า-2-ซีก-การวิเคราะห์-stakeholders--roles)
5. [แม่แบบ Structured Form-Based & Tabular Specifications](#5-แม่แบบ-structured-form-based--tabular-specifications)
6. [สาธิตการชำแหละโจทย์จริงทีละประโยค (Exam Dissection Walkthrough)](#6-สาธิตการชำแหละโจทย์จริงทีละประโยค-exam-dissection-walkthrough)
7. [ข้อผิดพลาดที่พบบ่อยและจุดที่มักโดนหักคะแนน (Common Pitfalls & Traps)](#7-ข้อผิดพลาดที่พบบ่อยและจุดที่มักโดนหักคะแนน)

---

# 1. โมเดลการทำข้อสอบ 3 ขั้นตอน (The 3-Step Exam Solving Engine)

```
[ ขั้นที่ 1: สแกนโจทย์หา Keyword ] ➔ [ ขั้นที่ 2: โยนลง 4 ถังความคิด ] ➔ [ ขั้นที่ 3: สวมสูตรโครงสร้างประโยค ]
```

1. **ขั้นที่ 1 (Skimming & Hunting):** อ่านโจทย์ภาษาอังกฤษแบบกวาดสายตาเร็วๆ ใช้ดินสอวงกลม **"คำกริยาการทำงาน"** (Action Verbs) และ **"ตัวเลขชี้วัด"** (Seconds, Users, %, Budget, Deadline)
2. **ขั้นที่ 2 (Categorization):** แยกข้อความที่วงกลมไว้ลง 4 ถังความคิด:
   * **[FR]** = ระบบทำอะไรได้บ้าง (กริยาการทำงาน)
   * **[NFR]** = ตัวเลขวัดความเร็ว ความจุ ความปลอดภัย (Metrics)
   * **[Domain]** = กฎหมาย PDPA/HIPAA หรือระบบเฉพาะขององค์กร
   * **[Constraints]** = บังคับภาษา/เฟรมเวิร์ก งบประมาณ กรอบเวลา
3. **ขั้นที่ 3 (Formulation):** นำมาประกอบเป็นประโยคคำตอบตามสูตรมาตรฐาน *"ระบบต้อง..."* หรือ *"The system shall..."*

---

# 2. ตาราง Keyword Hunting Matrix 4 ถังความคิด

| หมวดหมู่ | คีย์เวิร์ดภาษาอังกฤษที่พบบ่อยในโจทย์ | ความหมายและการตีความ | ตัวอย่างการแปลงไปตอบ |
| :--- | :--- | :--- | :--- |
| **1. Functional (FR)**<br>*(ระบบทำอะไร)* | `register`, `login`, `scan barcode/RFID`, `calculate price/fine`, `send notification/SMS/email`, `verify OTP/QR`, `generate daily report`, `pay via Mobile Banking` | หน้าที่หรือบริการที่ระบบส่งมอบให้ผู้ใช้งาน สามารถสั่งการให้เกิดขึ้นได้ | *ระบบต้องส่ง SMS แจ้งรหัส OTP 6 หลักให้ผู้รับเมื่อพัสดุเข้าตู้* |
| **2. Non-Functional (NFR)**<br>*(ทำงานได้ดีแค่ไหน)* | `within X seconds`, `X concurrent users`, `intuitive / user-friendly`, `without training / within X minutes`, `encrypted`, `99.9% availability`, `downtime < X s` | เกณฑ์คุณภาพและข้อจำกัดประสิทธิภาพ **ต้องมีตัวเลขชี้วัด (Metrics) เสมอ** | *ระบบต้องตอบสนองใน 2 วินาที และรองรับผู้ใช้พร้อมกัน 500 คน* |
| **3. Domain Reqs**<br>*(บริบทเฉพาะวงการ)* | `PDPA / GDPR`, `HIPAA / กระทรวงสาธารณสุข`, `Active Directory`, `Dewey Decimal / LCC`, `PromptPay standard`, `ISO standard` | กฎหมาย, มาตรฐานวิชาชีพ, หรือระบบเฉพาะขององค์กรนั้นๆ | *ระบบต้องปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล (PDPA)* |
| **4. Constraints**<br>*(ข้อจำกัดทีมพัฒนา)* | `built using Flutter/React/Java`, `run on Linux/Windows IoT`, `budget not exceeding X Baht`, `completed within X months` | ข้อจำกัดด้านภาษา เครื่องมือ งบประมาณ หรือเวลาที่ทีมพัฒนาต้องปฏิบัติตาม | *ต้องพัฒนาด้วย Flutter รองรับ iOS/Android งบไม่เกิน 250,000 บาท เสร็จใน 3 เดือน* |

---

# 3. สูตรสำเร็จรูปในการเขียนประโยคคำตอบ (Answering Formulas)

### 3.1 สูตร Functional Requirements (FR)
> 📌 **สูตรโครงสร้าง:**  
> **"ระบบต้อง + [อนุญาตให้ใคร / สั่งให้ทำอะไร] + [กริยาการทำงาน] + [ข้อมูลหรือผลลัพธ์] + [เงื่อนไขเพิ่มเติม]"**  
> *(EN: "The system shall [allow Actor to / automatically] + [Action Verb] + [Data/Object] + [when Condition].")*

* **ตัวอย่าง:**
  * *ระบบต้องอนุญาตให้นักศึกษาลงทะเบียนและเข้าสู่ระบบด้วยอีเมลของมหาวิทยาลัยได้*
  * *ระบบต้องคำนวณค่าธรรมเนียมการฝากเกินเวลาโดยอัตโนมัติหากฝากพัสดุไว้นานเกิน 48 ชั่วโมง*

---

### 3.2 สูตร Non-Functional Requirements (NFR 4 ด้านหลัก)
> ⚠️ **กฎเหล็กของ NFR:** ห้ามเขียนลอยๆ ว่า "ระบบต้องเร็ว" หรือ "ระบบต้องใช้ง่าย" (จะถูกหักคะแนนทันที) **ต้องมีตัวเลขชี้วัดเชิงปริมาณ (Measurable Metrics) เสมอ**

| มิติ NFR | สูตรโครงสร้างประโยค (Syntax Formula) | ตัวอย่างคำตอบที่ได้คะแนนเต็ม |
| :--- | :--- | :--- |
| **1. Usability**<br>*(ความง่ายในการใช้)* | ระบบต้องออกแบบให้ `[กลุ่มผู้ใช้]` สามารถ `[ทำภารกิจสำเร็จ]` ได้ภายในเวลา `[X นาที]` โดยมีอัตราความผิดพลาดน้อยกว่า `[Y%]` | *หน้าจอต้องใช้งานง่าย ผู้ใช้ใหม่สามารถทำรายการยืมหนังสือเสร็จได้ภายใน **30 วินาที** โดยไม่ต้องผ่านการฝึกอบรม* |
| **2. Performance**<br>*(ประสิทธิภาพความเร็ว)* | ระบบต้อง `[ตอบสนอง / ประมวลผลผลลัพธ์]` ภายในเวลาไม่เกิน `[X วินาที]` | *ระบบต้องแสดงผลการค้นหาข้อมูลภายในเวลาไม่เกิน **1.5 วินาที*** |
| **3. Capacity / Scalability**<br>*(การรองรับผู้ใช้)* | ระบบต้องรองรับผู้ใช้งานพร้อมกันอย่างน้อย `[X คน]` ในช่วงเวลาเร่งด่วน โดยระบบไม่ล่าช้าหรือหยุดทำงาน | *ระบบต้องรองรับผู้ใช้งานพร้อมกันอย่างน้อย **500 คน** ในช่วงเวลาเร่งด่วน (12:00-13:30)* |
| **4. Security**<br>*(ความปลอดภัย)* | ข้อมูล `[รหัสผ่าน / ข้อมูลการเงิน / ข้อมูลสุขภาพ]` ต้องได้รับการ `[เข้ารหัส / จำกัดสิทธิ์]` ตามมาตรฐานความปลอดภัย | *ข้อมูลการชำระเงินและรหัส OTP ต้องได้รับการเข้ารหัส (Encryption) ตลอดการส่งผ่านเครือข่าย* |

---

### 3.3 สูตร Domain Requirements
> 📌 **สูตรโครงสร้าง:**  
> **"ระบบต้อง [เชื่อมต่อกับระบบภายนอกเฉพาะด้าน / ปฏิบัติตามกฎเกณฑ์ทางกฎหมายหรือวิชาชีพนั้นๆ]"**

* **ตัวอย่าง:**
  * *ระบบต้องเชื่อมต่อกับฐานข้อมูล Active Directory ของมหาวิทยาลัยเพื่อยืนยันสถานะนักศึกษา*
  * *ระบบต้องปฏิบัติตาม พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล (PDPA) ในการจัดเก็บและทำลายข้อมูลผู้รับบริการ*

---

### 3.4 สูตร Constraints
> 📌 **สูตรโครงสร้าง:**  
> **"ทีมพัฒนาต้อง [ใช้เทคโนโลยี X] / โครงการต้อง [เสร็จใน Y เดือน] / งบประมาณต้อง [ไม่เกิน Z บาท]"**

* **ตัวอย่าง:**
  * *ทีมพัฒนาต้องใช้ Flutter Framework เพื่อให้แอปพลิเคชันรองรับทั้ง iOS และ Android จาก Codebase เดียวกัน*
  * *โครงการต้องพัฒนาและส่งมอบให้แล้วเสร็จภายในระยะเวลาไม่เกิน 3 เดือน*
  * *งบประมาณในการพัฒนาทั้งหมดต้องไม่เกิน 250,000 บาท*

---

# 4. สูตรผ่า 2 ซีก: การวิเคราะห์ Stakeholders & Roles

เมื่อโจทย์สั่งให้ระบุผู้มีส่วนได้ส่วนเสีย 5–7 กลุ่ม ให้ใช้สูตร **"ผ่าครึ่ง Internal vs External"**:

```
                              STAKEHOLDERS
                                   │
         ┌─────────────────────────┴─────────────────────────┐
         ▼                                                   ▼
  INTERNAL STAKEHOLDERS                               EXTERNAL STAKEHOLDERS
  (คนในโครงการ / ทีมพัฒนา)                             (คนนอก / ผู้ใช้ / องค์กรกำกับ)
  • เจ้าของโครงการ (Project Sponsor/Owner)             • ผู้ใช้งานปลายทาง (End Users / Customers)
  • พนักงานหน้างาน (Clinic Staff / Driver / Librarian)  • ผู้ให้บริการภายนอก (SMS/Payment Gateway)
  • ผู้จัดการแผนก (Manager / Supervisor)               • หน่วยงานกฎหมาย (Regulators / PDPA / สธ.)
  • ทีมโปรแกรมเมอร์และดีไซเนอร์ (Developers / UI)
  • ผู้ดูแลระบบ (System Administrator)
```

> 💡 **เคล็ดลับการเขียน Role (บทบาทหน้าที่):**  
> ❌ **อย่าเขียน:** *"ลูกค้า: เป็นคนซื้อของ"* (ได้คะแนนน้อย)  
> ✔️ **ต้องเขียน:** *"ลูกค้า (End User): ลงทะเบียนด้วยเบอร์โทร เลือกเมนู สั่งซื้อ ชำระเงินผ่าน Mobile Banking และรับใบเสร็จทาง Email"* (ได้คะแนนเต็ม)

---

# 5. แม่แบบ Structured Form-Based & Tabular Specifications

### 5.1 Form-Based Specification (ท่อง 10 ช่องมาตรฐาน)
1. **Function:** ชื่อฟังก์ชัน (เช่น `Calculate_Overdue_Fine`, `ICU_Risk_Alert`)
2. **Description:** บรรยายสั้นๆ ว่าฟังก์ชันนี้ทำอะไร
3. **Inputs:** ข้อมูลนำเข้ามีตัวแปรอะไรบ้าง (เช่น `OverdueDays`, `BookType`)
4. **Source:** แหล่งที่มาของข้อมูล (เช่น `Database Log`, `RFID Scanner`)
5. **Outputs:** ผลลัพธ์ที่ได้คือตัวแปรอะไร (เช่น `TotalFineAmount`, `AlarmLevel`)
6. **Destination:** ส่งผลลัพธ์ไปที่ใด (เช่น `Screen Display`, `Payment Gateway`)
7. **Action:** ขั้นตอนตรรกะการคำนวณ (If-Else logic)
8. **Pre-condition:** เงื่อนไขที่ต้องพร้อมก่อนเริ่มทำงาน
9. **Post-condition:** สิ่งที่จะเปลี่ยนไปหลังการทำงานเสร็จสิ้น
10. **Side Effects:** ผลข้างเคียงต่อระบบอื่น (ปกติระบุว่า `None`)

### 5.2 Tabular Specification (ตาราง Condition ➔ Action)
* ให้แบ่งคอลัมน์ฝั่งซ้ายเป็น **"เงื่อนไข (Conditions)"** และฝั่งขวาเป็น **"การกระทำ/ผลลัพธ์ (Action/Outputs)"** ให้ครอบคลุมทุกกรณีเสมอ รวมถึงกรณีค่าปกติ, ค่าเตือน, และค่าผิดพลาด (Error/Exception)

---

# 6. สาธิตการชำแหละโจทย์จริงทีละประโยค (Exam Dissection Walkthrough)

**[ข้อความโจทย์ภาษาอังกฤษ]:**
> *"FreshMart company is launching a 24/7 cashierless store. Customers scan their membership QR code to enter the gate. Overhead AI vision cameras and weight-sensor shelves track items picked up by shoppers. When walking out through the exit gate, the system automatically charges their credit card and sends an electronic receipt. The automated checkout must take less than 3 seconds per customer. The system must support at least 150 shoppers inside the store simultaneously. Customer camera streams and payment data must comply with Thailand's PDPA privacy laws. The software backend must be built using Python and deployed on Ubuntu Linux with a budget under 500,000 Baht within 4 months."*

**ผลลัพธ์การสกัดคำตอบ:**
* **Functional Requirements (FR):**
  1. ระบบต้องตรวจสอบ QR Code สมาชิกเพื่อปลดล็อกเปิดประตูทางเข้า
  2. ระบบต้องตรวจจับรายการสินค้าที่ลูกค้าหยิบจากชั้นวางโดยอัตโนมัติผ่านกล้อง AI และเซนเซอร์น้ำหนัก
  3. ระบบต้องตัดเงินผ่านบัตรเครดิตและส่งใบเสร็จอิเล็กทรอนิกส์ไปยังมือถือลูกค้าเมื่อเดินผ่านประตูทางออก
* **Non-Functional Requirements (NFR):**
  * *Performance & Usability:* ระบบต้องประมวลผลการเช็กเอาต์และคิดเงินเสร็จสิ้นภายในเวลาไม่เกิน **3 วินาที** ต่อคน
  * *Capacity:* ระบบต้องรองรับลูกค้าที่เดินเลือกสินค้าในร้านพร้อมกันอย่างน้อย **150 คน** โดยไม่เกิดความผิดพลาด
* **Domain Requirements:**
  * ระบบต้องจัดเก็บและประมวลผลภาพถ่ายวิดีโอจากกล้อง AI และข้อมูลการเงินให้สอดคล้องกับ พ.ร.บ. คุ้มครองข้อมูลส่วนบุคคล (PDPA)
* **Constraints:**
  * ระบบ Backend ต้องพัฒนาด้วยภาษา Python บนระบบปฏิบัติการ Ubuntu Linux
  * งบประมาณโครงการทั้งหมดต้องไม่เกิน 500,000 บาท
  * ระบบต้องพัฒนาและพร้อมเปิดให้บริการจริงภายในระยะเวลาไม่เกิน 4 เดือน

---

# 7. ข้อผิดพลาดที่พบบ่อยและจุดที่มักโดนหักคะแนน

1. **เขียน NFR แบบไม่มีตัวเลข (Goal ลอยๆ):** เขียนแค่ *"ระบบต้องเร็วและใช้ง่าย"* ❌ ➔ ต้องแก้เป็น *"ระบบต้องตอบสนองใน 2 วินาที และผู้ใช้ใหม่ทำรายการเสร็จใน 3 นาที"* ✔️
2. **สับสนระหว่าง Constraints กับ FR:** นำ *"ระบบต้องเขียนด้วย Flutter"* ไปตอบในช่อง FR ❌ ➔ ต้องนำไปตอบในช่อง **Constraints** เสมอ ✔️
3. **เขียน Domain Requirement เป็นฟังก์ชันธรรมดา:** นำ *"ระบบต้องมีปุ่มล็อกอิน"* ไปตอบในช่อง Domain ❌ ➔ ต้องตอบเฉพาะกฎหมาย PDPA หรือการเชื่อมต่อฐานข้อมูลเฉพาะของหน่วยงาน เช่น Active Directory ✔️
4. **เขียนบทบาท Stakeholder กว้างเกินไป:** เขียนแค่ *"แพทย์: เป็นคนตรวจคนไข้"* ❌ ➔ ต้องเขียนว่า *"แพทย์ (Internal): เข้าดูคิวนัดผ่าน Dashboard ตรวจรักษาผ่านวิดีโอ และสั่งจ่าย E-Prescription"* ✔️

---
*จัดทำขึ้นพิเศษเพื่อเป็นคู่มือวิเคราะห์ข้อสอบวิชา Software Engineering (SE) — ฝึกใช้สูตรนี้ทำข้อสอบ รับประกันคะแนนเต็มแน่นอนครับ! 💯*
