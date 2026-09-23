# Voice Data Integration & Architectural Ingestion Guide
## Project: software-engineering (Software Design & UML Wiki)

เอกสารฉบับนี้จัดทำขึ้นเพื่อระบุโครงสร้างสถาปัตยกรรมของโครงการ `software-engineering` อย่างละเอียดที่สุด และกำหนดแนวทางการบูรณาการข้อมูลการถอดความเสียง (Voice Transcripts), ภาพกระดาน/สไลด์ (Board Photos), กรณีศึกษา (Case Studies), และแนวข้อสอบปลายภาค (Use Case & Activity Diagrams) เข้าสู่ระบบ Wiki อย่างเป็นระบบ

---

## 1. การวิเคราะห์โครงสร้างโครงการ (Project Architectural Inventory)

โครงสร้างโฟลเดอร์ของ `C:\Project\software-engineering\` ประกอบด้วย:

```text
C:\Project\software-engineering\
├── 01_New_Slides_68/               <-- สไลด์ประกอบการสอนหลักสูตรใหม่ปี 2568-2569
├── 02_Old_Slides_Textbook/         <-- เอกสารและตำราเรียนอ้างอิง
├── 03_Exams_and_Cheatsheets/       <-- แนวข้อสอบและสรุปย่อก่อนสอบ
├── 04_Work_and_Homework/           <-- การบ้านและโจทย์เวิร์กช็อป (Use Case & Activity Diagram)
├── Transcripts/                    <-- แหล่งจัดเก็บ Verbatim Transcripts (.txt) จากไฟล์เสียงทุกสัปดาห์
└── Wiki/                           <-- บทเรียนและเอกสารอ้างอิง Obsidian Wiki
    ├── 01_New_Wiki_68/             <-- เนื้อหาบทเรียนฉบับสมบูรณ์
    ├── 03_Exams_and_Guides/        <-- คู่มือเตรียมสอบ
    └── 04_Work_and_Workshops/      <-- เวิร์กช็อปแก้โจทย์ (Lab_Equipment_Borrowing, Activity_Diagram)
```

---

## 2. แผนที่การนำข้อมูลเสียงและภาพเข้าสู่โปรเจกต์ (Voice & Image Ingestion Mapping)

| ข้อมูลนำเข้าจาก `C:\Project\Voice\` | ปลายทางใน `software-engineering\` | วัตถุประสงค์และการประมวลผล |
| :--- | :--- | :--- |
| **ไฟล์เสียงดิบ (.aac)** | ย้ายไป `C:\Project\Voice\Success\` | **ห้ามก๊อปปี้ไฟล์เสียงเข้าโปรเจกต์เด็ดขาด** แยก Audio Storage อย่างชัดเจน |
| **Verbatim Transcript (.txt)** | `Transcripts/20260922_093313.txt` | จัดเก็บเป็นเอกสารอ้างอิงคำต่อคำ 100% |
| **กรณีศึกษาระบบยืมคืนอุปกรณ์** | `Wiki/04_Work_and_Workshops/Lab_Equipment_Borrowing_Workshop.md` | บันทึกไดอะแกรม Use Case และคำอธิบายความสัมพันธ์ Actor Generalization |
| **บทเรียน Activity Diagram** | `Wiki/04_Work_and_Workshops/Activity_Diagram_Workshop.md` | บันทึกสัญลักษณ์ Decision, Merge, Fork & Join (Concurrency), Swimlanes |
| **จุดตัดคะแนนข้อสอบ Final** | `03_Exams_and_Cheatsheets/Final_Exam_UML_Guide.md` | จุดเตือนทิศทางลูกศร `<<include>>`, `<<extend>>` และการเขียนมุมมองระบบ |

---

## 3. สรุปสาระสำคัญและจุดลวงในข้อสอบปลายภาค (Final Exam Insights)

> **คำยืนยันจากอาจารย์ผู้สอน:**
> *"Use Case Diagram เนี่ย Confirm ครับ ออกใน Final แน่ๆ 1 ข้อ... และวันนี้ต่อเรื่อง Activity Diagram ก็จะเป็นอีก 1 ประเด็นที่จะปรากฏอยู่ใน Final เหมือนกัน... จาก Case Study เดียวกัน"*

1. **การวิเคราะห์ Actor & Generalization:**
   - คลาสแม่: `Member`
   - คลาสลูก: `Student` และ `Staff` (สืบทอดด้วยลูกศรสามเหลี่ยมโปร่ง `△` ชี้เข้าหา Member)
   - ผู้เกี่ยวข้องภายนอก: `Lab Officer` (อนุมัติ/ตรวจรับ) และ `Administrator` (จัดการระบบ)
2. **การใช้ Include vs Extend:**
   - `<<include>>`: บังคับทำเสมอ (ลูกศรพุ่งออกจาก Use Case หลัก $\rightarrow$ Use Case ย่อย) เช่น `Reserve Equipment` include `Check Availability` และ `Verify Eligibility`
   - `<<extend>>`: ทำเมื่อเข้าเงื่อนไขพิเศษ (ลูกศรพุ่งเข้าหา Use Case หลัก $\leftarrow$ Use Case ขยาย) เช่น `Request Special Approval` extend เข้าหา `Reserve Equipment` เฉพาะเมื่อของมูลค่า $> 100,000$ บาท
3. **การออกแบบ Activity Diagram:**
   - 1 Use Case ต้องอธิบายด้วย 1 Activity Diagram
   - จุดเริ่มต้น: วงกลมทึบ $\bullet$, จุดสิ้นสุด: วงกลมมีวงแหวน $\odot$
   - กิจกรรมเขียนในมุมมองของระบบ (System Workflow) ไม่ใช่มุมมอง User
   - แยกบทบาทด้วย **Swimlanes** และรองรับกิจกรรมคู่ขนานด้วย **Fork & Join**
