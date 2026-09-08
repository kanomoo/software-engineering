# 📖 ลำดับการอ่านสไลด์เรียน ภาคการศึกษา 2568 (Reading Order)

โฟลเดอร์นี้รวบรวมไฟล์สไลด์ PDF ทั้งหมด 12 ชุดของเทอม 2568 (New Curriculum) โดยจัดเรียงลำดับเนื้อหาตามสัปดาห์และบทเรียน เพื่อให้อ่านเข้าใจง่ายและต่อเนื่อง

---

## 🧭 แผนผังลำดับเนื้อหาเทอม 2568 (Curriculum Roadmap)

```text
[01] บทนำ & จรรยาบรรณวิศวกรซอฟต์แวร์
       ↓
[02 - 03] กระบวนการพัฒนาซอฟต์แวร์ (Waterfall, Incremental, Reuse & CMMI)
       ↓
[04 - 05] วิศวกรรมความต้องการ (Requirements Elicitation & Specification)
       ↓
[06 - 07] การสร้าง Use Case Diagram และสเปกข้อความ (Textual Specs)
       ↓
[08 - 09] ระเบียบวิธีแบบ Agile & Scrum Framework และ Burndown Chart
       ↓
[10 - 12] การทดสอบซอฟต์แวร์ (Ch6 Software Testing, Testing QA, White-Box & Cyclomatic Complexity)
```

---

## 📑 รายละเอียดเนื้อหาแต่ละไฟล์

| ลำดับไฟล์ | ชื่อไฟล์ | หัวข้อบทเรียน | เนื้อหาสำคัญที่ควรสังเกต |
|:---:|:---|:---|:---|
| **01** | `01_Ch1_Introduction.pdf` | **บทนำวิศวกรรมซอฟต์แวร์** | คุณลักษณะซอฟต์แวร์ที่ดี 4 ประการ, จรรยาบรรณ ACM/IEEE 8 ประการ, Case Studies (Mentcare, Insulin Pump) |
| **02** | `02_Ch2_SW_Processes.pdf` | **กระบวนการพัฒนา (Core)** | Waterfall, Incremental, Reuse-oriented, V-Model, การรับมือการเปลี่ยนแปลง และ Prototyping |
| **03** | `03_Ch2_Processes_Supplementary_l1.pdf` | **กระบวนการพัฒนา (เสริม)** | กิจกรรมในกระบวนการแบบเจาะลึก, วงจร CMMI Levels 1-5 และสไลด์บรรยายเพิ่มเติมในชั้นเรียน |
| **04** | `04_Ch4_Requirements_Engineering.pdf` | **วิศวกรรมความต้องการ (Sommerville)** | User vs System Requirements, Non-Functional Taxonomy (Product/Org/External), SRS โครงสร้างมาตรฐาน |
| **05** | `05_Ch4_Requirements_Cases_l2.pdf` | **ความต้องการและกรณีศึกษา** | เทคนิคการเก็บรวบรวม (Elicitation), Ethnography, การเขียน shall/should และกรณีศึกษาโจทย์ปฏิบัติการ |
| **06** | `06_UseCase_Modeling_Diagrams.pdf` | **Use Case Modeling** | สัญลักษณ์ UML Use Case, System Boundary, Actors, ความสัมพันธ์ `<<include>>`, `<<extend>>` และ Generalisation |
| **07** | `07_UseCase_Textual_Specifications_l3.pdf` | **Use Case Textual Specs** | ตารางเขียนสเปก Use Case ภาษาเขียน (Precondition, Basic Flow, Alternate Flow, Exception), โซลูชัน ATM & Library |
| **08** | `08_Agile_and_Scrum_Framework.pdf` | **Agile & Scrum** | Agile Manifesto 12 ประการ, บทบาทใน Scrum (PO, SM, Dev), พิธีกรรม (Sprint, Daily, Review, Retro), User Stories |
| **09** | `09_Scrum_Burndown_Chart.pdf` | **Burndown Chart** | การวิเคราะห์กราฟ Burndown Chart, Ideal Line vs Actual Effort, ปัญหา Scope Creep และการวัด Team Velocity |
| **10** | `10_Ch6_Software_Testing.pdf` | **สไลด์บทที่ 6: Testing (ฉบับเต็ม)** | ภาพรวมการทดสอบซอฟต์แวร์ของอาจารย์ (Verification & Validation, Test Case Design, Testing Strategies) |
| **11** | `11_Week9_Software_Testing_and_QA.pdf` | **การทดสอบซอฟต์แวร์ (Week 9)** | ระดับการทดสอบ (Unit, Integration, System, Acceptance), TDD, Black-Box (Equivalence Partitioning, BVA) |
| **12** | `12_Week10_Testing_Metrics_Cyclomatic.pdf` | **การวัดผลเชิงโครงสร้าง (Week 10)** | White-Box Testing, Flow Graph, Basis Path Testing, สูตร Cyclomatic Complexity $V(G) = E - N + 2$ |

---

## 💡 คำแนะนำในการอ่านและเตรียมสอบ
- สำหรับการเตรียมสอบกลางภาค (Midterm): ควรอ่านลำดับที่ **01 ถึง 09** อย่างละเอียด
- สำหรับการเตรียมสอบปลายภาค (Final): เน้นลำดับที่ **10 ถึง 12** ซึ่งครอบคลุมบท Testing ทั้งหมด
- สามารถเปิดเว็บข้อสอบจำลองและเฉลยเพื่อซ้อมทำควบคู่ได้ที่ **`03_Exams_and_Cheatsheets/Exam_Hub.html`**
