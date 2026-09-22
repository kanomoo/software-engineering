# 📋 เอกสารส่งงาน & เฉลยละเอียด: กรณีศึกษาระบบยืม–คืนอุปกรณ์ห้องปฏิบัติการมหาวิทยาลัย
## University Laboratory Equipment Borrowing System (Case Study 3 Solution)

> [!INFO] 🏷️ ข้อมูลกรณีศึกษาและเอกสารอ้างอิง
> - **วิชา:** วิศวกรรมซอฟต์แวร์ (Software Engineering) ภาคการศึกษา 2568
> - **เอกสารอ้างอิงโจทย์:** `04_Work_and_Homework/Use_Case_Diagram_Workshop/Lab_Equipment_Borrowing_System_Case_Study.pdf` (หรือ `casestudy-usecase.pdf`)
> - **ต้นแบบมาตรฐานการวิเคราะห์:** [[05_Case_Study_2_University_Registration|Case Study 2: University Course Registration System]]
> - **คู่มือทฤษฎี Use Case:** [[05_Use_Case_Diagrams|Lecture 4: Use Case Modeling & Diagrams]]
> - **หมวดหมู่:** 🔧 กรณีศึกษาขั้นสูง ครบทั้ง Actor Generalization, Use Case Generalization, `<<include>>`, และ `<<extend>>`

---

## 📸 แผนภาพเฉลยมาตรฐาน UML (ฉบับสมบูรณ์ — ไม่ใช้คำย่อ)

![UML Use Case Diagram](lab_equipment_usecase_diagram.png)

> [!TIP] 💡 ไฮไลท์การตรวจสอบความถูกต้อง 100% ตามมาตรฐาน UML:
> 1. **ห้ามเขียนย่อชื่อ Use Case:** ทุก Use Case ระบุชื่อเต็มด้วยโครงสร้าง **Verb + Object** (เช่น `Login with University SSO`, `Check Equipment Availability`, `Verify Member Permission`, `Request Special Approval`)
> 2. **Actor เป็นรูปคน (Stickman):** ใช้สัญลักษณ์ตัวคนตามมาตรฐานสากล โดยมี `Member` เป็น Super Actor และมี `Student` กับ `Staff` สืบทอดคุณสมบัติ
> 3. **Generalization (△):** ชี้จากตัวลูก (Sub) ขึ้นหาตัวแม่ (Super) ด้วย **หัวลูกศรสามเหลี่ยมโปร่ง** ทั้งในระดับ Actor และ Use Case
> 4. **`<<include>>` (ต้องทำเสมอ):** เส้นประหัวลูกศรแหลมเปิด พุ่งจาก **Base Case ➔ Included Case** (เช่น `Reserve Equipment` ➔ `Check Equipment Availability` และ `Verify Member Permission`)
> 5. **`<<extend>>` (ทำตามเงื่อนไข):** เส้นประหัวลูกศรแหลมเปิด พุ่งจาก **Extension Case ➔ Base Case** พร้อมระบุเงื่อนไขในวงเล็บ `[condition]`
> 6. **Dual-Role Use Case (สืบค้นตรง & บังคับตรวจตอนจอง):** `Check Equipment Availability` สมาชิกสามารถเรียกใช้งานได้โดยตรง (`Member ── Check Equipment Availability`) เพื่อตรวจดูคิวว่าง และในเวลาเดียวกันก็ถูก `Reserve Equipment` ดึงไปทำซ้ำแบบบังคับ (`<<include>>`) เพื่อยืนยันความพร้อมก่อนอนุมัติการจอง

---

## 📑 สารบัญเนื้อหา (Table of Contents)
1. [โจทย์ของระบบและกฎทางธุรกิจ (System Requirements & Business Rules)](#1-โจทย์ของระบบและกฎทางธุรกิจ)
2. [ขั้นตอนที่ 1: วิเคราะห์ Actor และ Actor Generalization Hierarchy](#2-ขั้นตอนที่-1-วิเคราะห์-actor-และ-actor-generalization-hierarchy)
3. [ขั้นตอนที่ 2: วิเคราะห์ Use Cases ทั้งหมดของระบบ (ห้ามใช้คำย่อ)](#3-ขั้นตอนที่-2-วิเคราะห์-use-cases-ทั้งหมดของระบบ)
4. [ขั้นตอนที่ 3: วิเคราะห์ความสัมพันธ์ «include» (บังคับทำเสมอ 100%)](#4-ขั้นตอนที่-3-วิเคราะห์ความสัมพันธ์-include-บังคับทำเสมอ-100)
5. [ขั้นตอนที่ 4: วิเคราะห์ความสัมพันธ์ «extend» (ทำเพิ่มเติมตามเงื่อนไขเฉพาะ)](#5-ขั้นตอนที่-4-วิเคราะห์ความสัมพันธ์-extend-ทำเพิ่มเติมตามเงื่อนไขเฉพาะ)
6. [ขั้นตอนที่ 5: วิเคราะห์ Use Case Generalization (เป้าหมายเดียวกัน หลากวิธี)](#6-ขั้นตอนที่-5-วิเคราะห์-use-case-generalization-เป้าหมายเดียวกัน-หลากวิธี)
7. [ตารางสรุปความสัมพันธ์ทั้งหมด (Relationship Matrix)](#7-ตารางสรุปความสัมพันธ์ทั้งหมด-relationship-matrix)
8. [ภาพรวม Use Case Diagram ที่สมบูรณ์แบบ (Full System Overview)](#8-ภาพรวม-use-case-diagram-ที่สมบูรณ์แบบ)
9. [แผนภาพแกนหลักตามที่อาจารย์สอนในห้องเรียน (In-Class Focus)](#9-แผนภาพแกนหลักตามที่อาจารย์สอนในห้องเรียน-in-class-focus)
10. [Key Takeaways, กระบวนการวิเคราะห์ 5 ขั้นตอน และ 4 คำถามชวนคิด](#10-key-takeaways-กระบวนการวิเคราะห์-5-ขั้นตอน-และ-4-คำถามชวนคิด)

---

## 1. โจทย์ของระบบและกฎทางธุรกิจ

*📄 อ้างอิงเอกสารโจทย์ `Lab_Equipment_Borrowing_System_Case_Study.pdf`*

มหาวิทยาลัยต้องการพัฒนา **ระบบยืม–คืนอุปกรณ์ห้องปฏิบัติการ (University Laboratory Equipment Borrowing System)** เพื่อจัดการอุปกรณ์ เช่น กล้องถ่ายภาพ, เครื่องวัดไฟฟ้า, ชุดไมโครคอนโทรลเลอร์, Notebook, เครื่องมือช่าง และอุปกรณ์เฉพาะทาง:

### 1.1 ความต้องการของระบบ (System Requirements)
1. **กลุ่มผู้ใช้บริการ:** ประกอบด้วย **นักศึกษา (Student)** และ **บุคลากรของมหาวิทยาลัย (Staff)** ซึ่งทั้งสองกลุ่มถือเป็น **สมาชิก (Member)** ของระบบ
2. **การเข้าสู่ระบบ:** สมาชิกทุกคนต้องเข้าสู่ระบบก่อนใช้งาน โดยรองรับ 2 ช่องทาง คือ เข้าสู่ระบบด้วยบัญชีมหาวิทยาลัย (`Login with University SSO`) หรือเข้าสู่ระบบด้วยชื่อผู้ใช้และรหัสผ่าน (`Login with Username and Password`)
3. **การสืบค้นและตรวจสอบ:** สมาชิกสามารถค้นหาอุปกรณ์ (`Search Equipment`), ดูรายละเอียดอุปกรณ์ (`View Equipment Detail`), ตรวจสอบสถานะความพร้อมใช้งาน (`Check Equipment Availability`) และดูประวัติการยืมของตนเอง (`View Borrowing History`)
4. **การจองอุปกรณ์ล่วงหน้า:** สมาชิกสามารถจองอุปกรณ์ (`Reserve Equipment`) ได้ โดยระบบต้องตรวจสอบสิทธิ์สมาชิก (`Verify Member Permission`) และตรวจสอบความพร้อมใช้งาน (`Check Equipment Availability`) ทุกครั้ง
5. **อุปกรณ์พิเศษ/มูลค่าสูง:** หากเป็นอุปกรณ์ที่กำหนดให้ต้องได้รับอนุญาตเป็นพิเศษ ระบบจะต้องทำการขออนุมัติอุปกรณ์พิเศษ (`Request Special Approval`) ไปยังเจ้าหน้าที่ห้องปฏิบัติการ (`Lab Officer`) ซึ่งเป็นผู้อนุมัติ (`Approve Special Equipment Request`)
6. **การรับอุปกรณ์ (ยืม):** เมื่อถึงวันนัดหมาย สมาชิกนำหลักฐานมาติดต่อเจ้าหน้าที่เพื่อทำรายการยืม (`Borrow Equipment`) โดยเจ้าหน้าที่ต้องตรวจสอบรายการจอง (`Verify Reservation`) และบันทึกรายการยืมพร้อมกำหนดวันคืน (`Record Borrowing Transaction`)
7. **การส่งคืนอุปกรณ์:** เมื่อนำอุปกรณ์มาคืน เจ้าหน้าที่จะทำรายการคืน (`Return Equipment`) โดยต้องตรวจสอบสภาพอุปกรณ์ (`Check Equipment Condition`) ทุกครั้ง หากคืนล่าช้าจะมีการคำนวณค่าปรับ (`Calculate Penalty`) และหากชำรุดเสียหายจะมีการรายงานความเสียหาย (`Report Equipment Damage`)
8. **การจัดการอุปกรณ์:** เจ้าหน้าที่ห้องปฏิบัติการสามารถจัดการข้อมูลอุปกรณ์ (`Manage Equipment`) เช่น เพิ่ม, แก้ไข หรือปรับปรุงสถานะ
9. **การดูแลระบบ:** ผู้ดูแลระบบ (`Administrator`) สามารถจัดการบัญชีผู้ใช้ (`Manage User Account`) และจัดการสิทธิ์ผู้ใช้งาน (`Manage User Permission`)

### 1.2 เงื่อนไขสำคัญทางธุรกิจ (Business Rules & Constraints)
* **Rule 1 (Authentication Generalization):** การล็อกอินมีเป้าหมายร่วมกันคือการยืนยันตัวตน แต่มี 2 วิธีการดำเนินงานเฉพาะทาง คือ `Login with University SSO` และ `Login with Username and Password`
* **Rule 2 (Mandatory Verification on Reservation):** ทุกครั้งที่สมาชิกกดจองอุปกรณ์ ระบบต้องตรวจสอบความพร้อมใช้งานของอุปกรณ์และตรวจสอบสิทธิ์ของสมาชิกก่อนเสมอ ขาดขั้นตอนใดขั้นตอนหนึ่งไม่ได้ (`<<include>>`)
* **Rule 3 (Special Equipment Approval Extension):** เฉพาะกรณีที่อุปกรณ์มีมูลค่าสูงหรือเป็นอุปกรณ์พิเศษเท่านั้น จึงจะเกิดขั้นตอนการขออนุมัติพิเศษ (`<<extend>> [Special / High-Value Equipment]`)
* **Rule 4 (Mandatory Verification on Borrow & Inspection on Return):** ทุกครั้งที่มีการส่งมอบอุปกรณ์ ต้องตรวจใบจองและบันทึกวันคืนเสมอ (`<<include>>`) และทุกครั้งที่รับคืน ต้องตรวจสภาพอุปกรณ์เสมอ (`<<include>>`)
* **Rule 5 (Penalty & Damage Extensions on Return):** การคำนวณค่าปรับเกิดขึ้นเฉพาะเมื่อคืนอุปกรณ์ล่าช้า (`<<extend>> [Overdue]`) และการรายงานความเสียหายเกิดขึ้นเฉพาะเมื่อพบอุปกรณ์ชำรุด (`<<extend>> [Damaged]`)

---

## 2. ขั้นตอนที่ 1: วิเคราะห์ Actor และ Actor Generalization Hierarchy

### 2.1 รายชื่อ Actors ในระบบ
| Actor | บทบาทในระบบ (Role) | เป้าหมายหลัก (Main Goal) | ประเภท Actor |
|:---|:---|:---|:---|
| **Member** | สมาชิกผู้ใช้บริการ | ค้นหา, ตรวจสอบความพร้อม, จอง, ยืม, คืนอุปกรณ์ และดูประวัติ | Human (Super Actor ฝั่งผู้ใช้บริการ) |
| **Student** | นักศึกษา | เข้าใช้งานระบบตามสิทธิ์ของนักศึกษา | Human (Sub-Actor ของ Member) |
| **Staff** | บุคลากรของมหาวิทยาลัย | ยืมอุปกรณ์วิจัยและอุปกรณ์เฉพาะทางเพิ่มเติม | Human (Sub-Actor ของ Member) |
| **Lab Officer** | เจ้าหน้าที่ห้องปฏิบัติการ | ส่งมอบอุปกรณ์, รับคืน, ตรวจสภาพ, อนุมัติคำขอพิเศษ และจัดการอุปกรณ์ | Human (Standalone Operational Actor - แยกอิสระ) |
| **Administrator** | ผู้ดูแลระบบ | จัดการบัญชีผู้ใช้ และกำหนดสิทธิ์การเข้าใช้งานในระบบ | Human (Standalone Administrative Actor - แยกอิสระ) |

---

### 2.2 โครงสร้างลำดับชั้นของ Actor (Actor Generalization Hierarchy)

#### 🎯 แบบที่ 1: โครงสร้างมาตรฐานตามโจทย์และในห้องเรียน (In-Class & Workshop Standard) ★ สำหรับส่งงาน
ตามโจทย์ข้อที่ 1 ระบุชัดเจนว่า **นักศึกษา (Student)** และ **บุคลากร (Staff)** ทั้งสองกลุ่มถือเป็น **สมาชิก (Member)** ของระบบ จึงจัดกลุ่มสืบทอดคุณสมบัติ (Generalization) เข้าหา `Member` ส่วน **Lab Officer** และ **Administrator** เป็นผู้ดูแลระบบที่ปฏิบัติหน้าที่คนละบทบาท จึงแยกเดี่ยวเป็นอิสระ:

```mermaid
flowchart BT
    subgraph InClass_Actor_Hierarchy ["โครงสร้าง Actor Generalization ตามโจทย์และในห้องเรียน"]
        direction BT
        
        Member["👤 Member<br/>(สมาชิกผู้ใช้บริการ - Super Actor)"]
        Student["🧑‍🎓 Student<br/>(นักศึกษา - Sub Actor)"]
        Staff["👨‍🏫 Staff<br/>(บุคลากรผู้ยืม - Sub Actor)"]

        Student -->|"is-a (△)"| Member
        Staff -->|"is-a (△)"| Member

        subgraph Independent_Actors ["ผู้ปฏิบัติการและผู้ดูแลระบบ (แยกเดี่ยวอิสระ)"]
            direction TB
            LabOfficer["👨‍🔬 Lab Officer<br/>(เจ้าหน้าที่ห้องปฏิบัติการ)"]
            Admin["🛡️ Administrator<br/>(ผู้ดูแลระบบ)"]
        end
    end

    style Member fill:#e0f2fe,stroke:#0284c7,stroke-width:2.5px
    style Student fill:#ffffff,stroke:#475569,stroke-width:1.5px
    style Staff fill:#ffffff,stroke:#475569,stroke-width:1.5px
    style LabOfficer fill:#fff7ed,stroke:#ea580c,stroke-width:2px
    style Admin fill:#f5f3ff,stroke:#7c3aed,stroke-width:2px
    style Independent_Actors fill:#f8fafc,stroke:#cbd5e1,stroke-dasharray: 4 4
```

#### 💡 กฎเหล็กของ Actor Generalization:
1. **ทิศทางหัวลูกศร (is-a):** ต้องชี้จาก **ตัวลูก (Sub-Actor: Student, Staff)** พุ่งเข้าหา **ตัวแม่ (Super-Actor: Member)** เสมอ ด้วย **หัวลูกศรสามเหลี่ยมโปร่ง (△)**
2. **การสืบทอดความสัมพันธ์ (Inheritance):** เมื่อ `Student` และ `Staff` สืบทอดมาจาก `Member` ทั้งสองกลุ่มจะได้รับสิทธิ์เข้าถึง Use Cases ทั้งหมดที่เชื่อมกับ `Member` ทันที โดยไม่ต้องลากเส้นซ้ำซ้อน
3. **การแยกบทบาท (Separation of Roles):**
   - **`Staff` ทางซ้าย:** หมายถึงอาจารย์/นักวิจัย/เจ้าหน้าที่มหาวิทยาลัยที่มา **ขอยืมอุปกรณ์** (เป็น Sub-Actor ของ `Member`)
   - **`Lab Officer` ทางขวา:** คือเจ้าหน้าที่ประจำห้องแล็บที่ทำหน้าที่ **ส่งมอบ/รับคืน/ตรวจสภาพ/อนุมัติคำขอ** (เป็น Operational Actor แยกอิสระ)
   - **`Administrator` ทางขวา:** คือผู้ดูแลระบบที่ทำหน้าที่ **จัดการบัญชีและสิทธิ์** (เป็น Administrative Actor แยกอิสระ)

---

## 3. ขั้นตอนที่ 2: วิเคราะห์ Use Cases ทั้งหมดของระบบ

> [!IMPORTANT] 📌 กฎเหล็ก: ห้ามเขียนย่อชื่อ Use Case!
> ชื่อ Use Case ทุกตัวต้องขึ้นต้นด้วย **คำกริยา (Verb) ตามด้วยกรรม/ส่วนขยาย (Object)** อย่างชัดเจนเสมอ เช่น:
> - ❌ `SSO` ➔ ✔️ `Login with University SSO`
> - ❌ `UP` ➔ ✔️ `Login with Username and Password`
> - ❌ `Check` ➔ ✔️ `Check Equipment Availability`
> - ❌ `Verify` ➔ ✔️ `Verify Member Permission`
> - ❌ `Reserve` ➔ ✔️ `Reserve Equipment`
> - ❌ `Approval` ➔ ✔️ `Request Special Approval`

### รายการ Use Cases แบ่งตามหมวดหมู่การทำงาน (Total 15 Use Cases):
1. **หมวดการเข้าสู่ระบบ (Authentication):**
   * `Login` — เข้าสู่ระบบเพื่อยืนยันตัวตน (General Use Case)
   * `Login with University SSO` — เข้าสู่ระบบด้วยบัญชีมหาวิทยาลัย (Specialized Use Case)
   * `Login with Username and Password` — เข้าสู่ระบบด้วยชื่อผู้ใช้และรหัสผ่าน (Specialized Use Case)
2. **หมวดการสืบค้นและตรวจสอบ (Search & Inquiry):**
   * `Search Equipment` — ค้นหาอุปกรณ์ตามประเภท รหัส หรือชื่อ
   * `View Equipment Detail` — ดูรายละเอียด สถานที่จัดเก็บ และคุณสมบัติ
   * `Check Equipment Availability` — ตรวจสอบสถานะความพร้อมใช้งาน (ว่าง/ถูกจอง/กำลังถูกยืม) โดยผู้ใช้สามารถสืบค้นดูตารางคิวว่างได้โดยตรง (Standalone Action) และถูกเรียกใช้ซ้ำแบบบังคับเมื่อจองอุปกรณ์ (Included Case)
   * `View Borrowing History` — ดูประวัติการยืม–คืนของตนเอง
3. **หมวดการจองอุปกรณ์ (Reservation Workflow):**
   * `Reserve Equipment` — ทำรายการจองอุปกรณ์ล่วงหน้า (Base Use Case)
   * `Verify Member Permission` — ตรวจสอบสิทธิ์ของสมาชิกตามประเภท (Included Use Case)
   * `Request Special Approval` — ยื่นคำขออนุมัติการใช้อุปกรณ์พิเศษ/มูลค่าสูง (Extension Use Case)
   * `Approve Special Equipment Request` — อนุมัติคำขอใช้อุปกรณ์พิเศษ (โดยเจ้าหน้าที่ห้องปฏิบัติการ)
4. **หมวดการยืมและคืนอุปกรณ์ (Borrow & Return Operations):**
   * `Borrow Equipment` — ส่งมอบและทำรายการยืมอุปกรณ์ (Base Use Case)
   * `Verify Reservation` — ตรวจสอบรายการจองก่อนส่งมอบ (Included Use Case)
   * `Record Borrowing Transaction` — บันทึกรายการยืมและกำหนดวันครบกำหนดคืน (Included Use Case)
   * `Return Equipment` — รับคืนอุปกรณ์ (Base Use Case)
   * `Check Equipment Condition` — ตรวจสอบสภาพอุปกรณ์เมื่อรับคืน (Included Use Case)
   * `Calculate Penalty` — คำนวณค่าปรับกรณีส่งคืนเกินกำหนดเวลา (Extension Use Case)
   * `Report Equipment Damage` — บันทึกรายงานความเสียหายของอุปกรณ์ (Extension Use Case)
5. **หมวดการบริหารจัดการระบบ (Management & Administration):**
   * `Manage Equipment` — จัดการข้อมูลอุปกรณ์ในระบบ (เพิ่ม/แก้ไข/ปรับปรุงสถานะ)
   * `Manage User Account` — จัดการบัญชีผู้ใช้งานระบบ
   * `Manage User Permission` — กำหนดและจัดการสิทธิ์ผู้ใช้งาน

---

## 4. ขั้นตอนที่ 3: วิเคราะห์ความสัมพันธ์ «include» (บังคับทำเสมอ 100%)

ความสัมพันธ์แบบ `<<include>>` แสดงถึงพฤติกรรมย่อยที่ Use Case หลัก **ต้องเรียกใช้เสมอ 100%** หากขาดพฤติกรรมนี้ Use Case หลักจะไม่สามารถทำงานสำเร็จได้

```mermaid
flowchart LR
    subgraph Reservation_Include ["1. กระบวนการจองอุปกรณ์"]
        direction LR
        RE(["Reserve Equipment<br/>(จองอุปกรณ์ล่วงหน้า)"]) -.->|«include»| CEA(["Check Equipment Availability<br/>(ตรวจความพร้อมอุปกรณ์เสมอ)"])
        RE -.->|«include»| VMP(["Verify Member Permission<br/>(ตรวจสิทธิ์สมาชิกเสมอ)"])
    end

    subgraph Borrow_Include ["2. กระบวนการยืมอุปกรณ์"]
        direction LR
        BE(["Borrow Equipment<br/>(ยืมอุปกรณ์)"]) -.->|«include»| VR(["Verify Reservation<br/>(ตรวจรายการจองเสมอ)"])
        BE -.->|«include»| RBT(["Record Borrowing Transaction<br/>(บันทึกรายการยืมและวันคืน)"])
    end

    subgraph Return_Include ["3. กระบวนการคืนอุปกรณ์"]
        direction LR
        RTE(["Return Equipment<br/>(คืนอุปกรณ์)"]) -.->|«include»| CEC(["Check Equipment Condition<br/>(ตรวจสภาพอุปกรณ์เสมอ)"])
    end

    style RE fill:#fce4ec,stroke:#c2185b,stroke-width:2px
    style BE fill:#f0f4c3,stroke:#9e9d24,stroke-width:2px
    style RTE fill:#fff9c4,stroke:#fbc02d,stroke-width:2px
```

### เหตุผลและหลักการของ `<<include>>`:
1. **ต้องเกิดขึ้นเสมอ 100%:** ทุกครั้งที่สมาชิกกดจองอุปกรณ์ (`Reserve Equipment`) ระบบจะยืนยันการจองไม่ได้เลย หากยังไม่ได้ตรวจว่าอุปกรณ์ว่างจริงหรือไม่ และผู้ใช้มีสิทธิ์ยืมอุปกรณ์นั้นหรือไม่
2. **Reuse พฤติกรรมร่วม และ Dual-Role Use Case:** พฤติกรรมการตรวจความพร้อมของอุปกรณ์ (`Check Equipment Availability`) สามารถทำหน้าที่ได้ 2 สถานะ: สมาชิกเรียกใช้โดยตรงเพื่อดูคิวว่าง และระบบเรียกใช้อีกครั้งแบบบังคับ 100% ผ่าน `<<include>>` เมื่อทำการจอง เพื่อรับประกันว่าจะไม่มีการจองชนกัน
3. **ทิศทางลูกศร:** ชี้จาก **Base Use Case ──[«include»]──> Included Use Case** เสมอ

---

## 5. ขั้นตอนที่ 4: วิเคราะห์ความสัมพันธ์ «extend» (ทำเพิ่มเติมตามเงื่อนไขเฉพาะ)

ความสัมพันธ์แบบ `<<extend>>` แสดงถึงพฤติกรรมส่วนขยายที่จะทำงาน **เฉพาะเมื่อตรงตามเงื่อนไขที่กำหนด (Guard Condition)** เท่านั้น ในสภาวะปกติ Base Use Case สามารถทำงานสำเร็จได้โดยไม่ต้องเรียกใช้ Extension

```mermaid
flowchart LR
    RSA(["Request Special Approval<br/>(ขออนุมัติอุปกรณ์พิเศษ)"]) -.->|"«extend»<br/>[Special / High-Value Equipment]"| RE(["Reserve Equipment<br/>(Base Use Case)"])

    CP(["Calculate Penalty<br/>(คำนวณค่าปรับ)"]) -.->|"«extend»<br/>[Overdue / คืนล่าช้า]"| RTE(["Return Equipment<br/>(Base Use Case)"])

    RED(["Report Equipment Damage<br/>(รายงานความเสียหาย)"]) -.->|"«extend»<br/>[Damaged / ชำรุดเสียหาย]"| RTE

    style RE fill:#fce4ec,stroke:#c2185b,stroke-width:2px
    style RTE fill:#fff9c4,stroke:#fbc02d,stroke-width:2px
    style RSA fill:#fff3e0,stroke:#e65100
    style CP fill:#fff3e0,stroke:#e65100
    style RED fill:#fff3e0,stroke:#e65100
```

### เหตุผลและหลักการของ `<<extend>>`:
1. **เกิดขึ้นเฉพาะบางสถานการณ์ (Conditional Behavior):** ในการจองอุปกรณ์ทั่วไป สมาชิกสามารถจองสำเร็จได้ทันที แต่ถ้าอุปกรณ์นั้นเข้าเงื่อนไข `[Special / High-Value Equipment]` ระบบจึงจะขยายการทำงานไปขออนุมัติ
2. **เงื่อนไขการขยาย (Extension Points & Guard Conditions):**
   * เกิดขึ้นเมื่อ: `[Special / High-Value Equipment]` ➔ ขยายไปยัง `Request Special Approval`
   * เกิดขึ้นเมื่อ: `[Overdue / คืนล่าช้า]` ➔ ขยายไปยัง `Calculate Penalty`
   * เกิดขึ้นเมื่อ: `[Damaged / ชำรุดเสียหาย]` ➔ ขยายไปยัง `Report Equipment Damage`
3. **Base Use Case สมบูรณ์ได้ด้วยตนเอง:** การยืม-คืนตามปกติส่วนใหญ่จะเสร็จสิ้นโดยไม่มีค่าปรับและไม่มีความเสียหาย
4. **ทิศทางลูกศร:** ชี้จาก **Extension Use Case ──[«extend»]──> Base Use Case** เสมอ

---

## 6. ขั้นตอนที่ 5: วิเคราะห์ Use Case Generalization (เป้าหมายเดียวกัน หลากวิธี)

Use Case Generalization ใช้เมื่อ Use Case มี **เป้าหมายเดียวกัน (Same Goal)** แต่มี **วิธีการดำเนินการหรืออัลกอริทึมที่แตกต่างกันเฉพาะทาง (Specialized Variants)**:

```mermaid
flowchart BT
    SSO(["Login with University SSO<br/>(เข้าสู่ระบบด้วยบัญชีมหาวิทยาลัย)"]) -->|"is-a (สืบทอด)"| LOGIN(["Login<br/>(เป้าหมายร่วม: เข้าสู่ระบบเพื่อยืนยันตัวตน)"])
    UP(["Login with Username and Password<br/>(เข้าสู่ระบบด้วยชื่อผู้ใช้และรหัสผ่าน)"]) -->|"is-a (สืบทอด)"| LOGIN

    style LOGIN fill:#e3f2fd,stroke:#1565c0,stroke-width:2px
    style SSO fill:#ffffff,stroke:#1565c0
    style UP fill:#ffffff,stroke:#1565c0
```

* **เป้าหมายร่วม (General Goal):** สมาชิกต้องการเข้าสู่ระบบเพื่อยืนยันตัวตน (`Login`)
* **วิธีการเฉพาะทาง (Specialized Methods):**
  1. `Login with University SSO` (ผ่าน Identity Provider ของมหาวิทยาลัย)
  2. `Login with Username and Password` (ผ่านฐานข้อมูลบัญชีผู้ใช้ของระบบโดยตรง)
* **สัญลักษณ์:** เส้นทึบปลายลูกศรเป็น **หัวสามเหลี่ยมโปร่ง (△)** ชี้จากตัวลูกขึ้นหาตัวแม่

---

## 7. ตารางสรุปความสัมพันธ์ทั้งหมด (Relationship Matrix)

| ประเภทความสัมพันธ์ | Use Case ต้นทาง (From) | Use Case ปลายทาง (To) | เหตุผลและเงื่อนไข (Meaning / Reason) |
|:---|:---|:---|:---|
| **Actor Generalization** | `Student` | `Member` | `Student is-a Member` (สืบทอดสิทธิ์การใช้งานทั่วไป) |
| **Actor Generalization** | `Staff` | `Member` | `Staff is-a Member` (สืบทอดสิทธิ์การใช้งานทั่วไป) |
| **Use Case Generalization** | `Login with University SSO` | `Login` | รูปแบบการเข้าสู่ระบบด้วย Single Sign-On |
| **Use Case Generalization** | `Login with Username and Password` | `Login` | รูปแบบการเข้าสู่ระบบด้วยชื่อผู้ใช้และรหัสผ่าน |
| **Association (สืบค้นตรง)** | `Member` | `Check Equipment Availability` | สมาชิกสามารถตรวจสอบสถานะความพร้อมใช้งานของอุปกรณ์ได้โดยตรงด้วยตนเอง (Standalone Action) |
| **`<<include>>`** | `Reserve Equipment` | `Check Equipment Availability` | ต้องตรวจความพร้อมของอุปกรณ์เสมอทุกครั้งที่จอง (ป้องกันการจองชนเวลา) |
| **`<<include>>`** | `Reserve Equipment` | `Verify Member Permission` | ต้องตรวจสิทธิ์ของสมาชิกเสมอทุกครั้งที่จอง |
| **`<<extend>>`** | `Request Special Approval` | `Reserve Equipment` | ทำเมื่อ `[Special / High-Value Equipment]` เท่านั้น |
| **`<<include>>`** | `Borrow Equipment` | `Verify Reservation` | เจ้าหน้าที่ต้องตรวจสอบใบจองก่อนส่งมอบอุปกรณ์เสมอ |
| **`<<include>>`** | `Borrow Equipment` | `Record Borrowing Transaction` | ต้องบันทึกรายการยืมและกำหนดวันคืนเสมอ |
| **`<<include>>`** | `Return Equipment` | `Check Equipment Condition` | เจ้าหน้าที่ต้องตรวจสภาพอุปกรณ์ทุกครั้งที่รับคืน |
| **`<<extend>>`** | `Calculate Penalty` | `Return Equipment` | ทำเมื่อ `[Overdue / คืนอุปกรณ์เกินกำหนด]` เท่านั้น |
| **`<<extend>>`** | `Report Equipment Damage` | `Return Equipment` | ทำเมื่อ `[Damaged / ตรวจพบอุปกรณ์ชำรุดเสียหาย]` เท่านั้น |

---

## 8. ภาพรวม Use Case Diagram ที่สมบูรณ์แบบ

```mermaid
flowchart LR
    subgraph Boundary ["System Boundary: University Laboratory Equipment Borrowing System"]
        direction TB

        %% Authentication & Inquiry Group
        subgraph Group1 ["1. Authentication & Inquiry (การยืนยันตัวตนและการสืบค้น)"]
            direction TB
            U_LOGIN(["Login (เข้าสู่ระบบ)"])
            U_SSO(["Login with University SSO"])
            U_UP(["Login with Username and Password"])
            
            U_SSO -->|is-a| U_LOGIN
            U_UP -->|is-a| U_LOGIN

            U_SEARCH(["Search Equipment (ค้นหาอุปกรณ์)"])
            U_VIEW(["View Equipment Detail (ดูรายละเอียด)"])
            U_HIST(["View Borrowing History (ดูประวัติการยืม-คืน)"])
        end

        %% Reservation Workflow Group
        subgraph Group2 ["2. Reservation Workflow (การจองอุปกรณ์ - In-Class Focus)"]
            direction TB
            U_RESERVE(["Reserve Equipment (จองอุปกรณ์)"])
            U_CHK_AVAIL(["Check Equipment Availability (ตรวจความพร้อม)"])
            U_VER_PERM(["Verify Member Permission (ตรวจสิทธิ์สมาชิก)"])
            U_REQ_SPEC(["Request Special Approval (ขออนุมัติพิเศษ)"])

            U_RESERVE -.->|«include»| U_CHK_AVAIL
            U_RESERVE -.->|«include»| U_VER_PERM
            U_REQ_SPEC -.->|"«extend» [Special Equipment]"| U_RESERVE
        end

        %% Borrow Operations Group
        subgraph Group3 ["3. Borrow Operations (การส่งมอบและยืมอุปกรณ์)"]
            direction TB
            U_BORROW(["Borrow Equipment (ยืมอุปกรณ์)"])
            U_VER_RES(["Verify Reservation (ตรวจรายการจอง)"])
            U_REC_BORROW(["Record Borrowing Transaction (บันทึกรายการยืม)"])

            U_BORROW -.->|«include»| U_VER_RES
            U_BORROW -.->|«include»| U_REC_BORROW
        end

        %% Return Operations Group
        subgraph Group4 ["4. Return Operations (การคืนและตรวจสภาพอุปกรณ์)"]
            direction TB
            U_RETURN(["Return Equipment (คืนอุปกรณ์)"])
            U_CHK_COND(["Check Equipment Condition (ตรวจสภาพ)"])
            U_CALC_PEN(["Calculate Penalty (คำนวณค่าปรับ)"])
            U_REP_DMG(["Report Equipment Damage (รายงานความเสียหาย)"])

            U_RETURN -.->|«include»| U_CHK_COND
            U_CALC_PEN -.->|"«extend» [Overdue]"| U_RETURN
            U_REP_DMG -.->|"«extend» [Damaged]"| U_RETURN
        end

        %% Management Group
        subgraph Group5 ["5. Management & Administration (การจัดการระบบ)"]
            direction TB
            U_APP_SPEC(["Approve Special Equipment Request (อนุมัติคำขอพิเศษ)"])
            U_MAN_EQ(["Manage Equipment (จัดการอุปกรณ์)"])
            U_MAN_USER(["Manage User Account (จัดการบัญชีผู้ใช้)"])
            U_MAN_PERM(["Manage User Permission (จัดการสิทธิ์ผู้ใช้งาน)"])
        end
    end

    %% Left Actors: Generalization & Primary User
    ACT_STU["🧑‍🎓 Student"] -->|is-a| ACT_MEM["👤 Member"]
    ACT_STAFF["👨‍🏫 Staff"] -->|is-a| ACT_MEM

    %% Clean Association Fan-out from Member (No Crossing)
    ACT_MEM --- U_LOGIN
    ACT_MEM --- U_SEARCH
    ACT_MEM --- U_VIEW
    ACT_MEM --- U_CHK_AVAIL
    ACT_MEM --- U_HIST
    ACT_MEM --- U_RESERVE
    ACT_MEM --- U_BORROW
    ACT_MEM --- U_RETURN

    %% Right Actors: Secondary & Administration
    U_APP_SPEC --- ACT_OFFICER["👨‍🔬 Lab Officer"]
    U_BORROW --- ACT_OFFICER
    U_RETURN --- ACT_OFFICER
    U_MAN_EQ --- ACT_OFFICER

    ACT_ADMIN["🛡️ Administrator"] --- U_MAN_USER
    ACT_ADMIN --- U_MAN_PERM

    style Boundary fill:#ffffff,stroke:#0f172a,stroke-width:2.5px
    style ACT_MEM fill:#e0f2fe,stroke:#0284c7,stroke-width:2.5px
    style ACT_STU fill:#ffffff,stroke:#475569
    style ACT_STAFF fill:#ffffff,stroke:#475569
    style ACT_OFFICER fill:#fff7ed,stroke:#ea580c,stroke-width:2.5px
    style ACT_ADMIN fill:#f5f3ff,stroke:#7c3aed,stroke-width:2.5px
    style U_RESERVE fill:#fce7f3,stroke:#db2777,stroke-width:2px
    style U_BORROW fill:#fef08a,stroke:#ca8a04,stroke-width:2px
    style U_RETURN fill:#bbf7d0,stroke:#16a34a,stroke-width:2px
    style U_LOGIN fill:#e0f2fe,stroke:#0284c7,stroke-width:2px
```

---

## 9. แผนภาพแกนหลักตามที่อาจารย์สอนในห้องเรียน (In-Class Focus)

ในห้องเรียน อาจารย์ได้เน้นย้ำจุดตัดคะแนนสำคัญ 4 ประการบนกระดาน โดยเขียนสรุปแบบย่อไว้ดังนี้:
- กล่อง Generalization ของ Login: `SSO` และ `UP` พุ่งเข้าหา `Login`
- กล่อง Core: `Reserve Equipment` พุ่งไปหา `Check Equipment Availability` และ `Verify Member Permission` ด้วย `<<include>>`
- ส่วนต่อขยาย: `Request Special Approval` พุ่งขึ้นหา `Reserve Equipment` ด้วย `<<extend>>`
- ตัวคนด้านขวา: `Lab Officer` เชื่อมโยงกับ `Approval`

เมื่อแปลงเป็น **ชื่อทางการแบบไม่ย่อ** ตามข้อกำหนดทางวิชาการ (จัดเส้นแนวนอน Left-to-Right ให้ไหลลื่น ไม่มีเส้นตัดขวาง):

```mermaid
flowchart LR
    subgraph Boundary ["System Boundary: ระบบยืม–คืนอุปกรณ์ห้องปฏิบัติการ"]
        direction LR

        subgraph Generalization_Login ["Use Case Generalization: การเข้าสู่ระบบ"]
            direction TB
            LOGIN(["Login<br/>(เข้าสู่ระบบ)"])
            SSO(["Login with University SSO<br/>(เข้าสู่ระบบด้วยบัญชีมหาวิทยาลัย)"])
            UP(["Login with Username and Password<br/>(เข้าสู่ระบบด้วยชื่อผู้ใช้และรหัสผ่าน)"])

            SSO -->|is-a| LOGIN
            UP -->|is-a| LOGIN
        end

        subgraph Catalog ["การสืบค้น"]
            direction TB
            SEARCH(["Search Equipment<br/>(ค้นหาอุปกรณ์)"])
            VIEW(["View Equipment Detail<br/>(ดูรายละเอียดอุปกรณ์)"])
        end

        subgraph Core_Reservation ["แกนหลัก: การจอง, การตรวจสอบ และการขออนุมัติ"]
            direction TB
            RESERVE(["Reserve Equipment<br/>(จองอุปกรณ์)"])
            CHECK(["Check Equipment Availability<br/>(ตรวจความพร้อมอุปกรณ์) ✔"])
            VERIFY(["Verify Member Permission<br/>(ตรวจสิทธิ์สมาชิก) ✔"])
            APPROVAL(["Request Special Approval<br/>(ขออนุมัติอุปกรณ์พิเศษ)"])

            %% include: จากตัวหลัก Reserve พุ่งไปหาตัวย่อย Check และ Verify
            RESERVE -.->|«include»| CHECK
            RESERVE -.->|«include»| VERIFY

            %% extend: จากตัวเสริม Approval พุ่งขึ้นไปหาตัวหลัก Reserve
            APPROVAL -.->|"«extend»<br/>[อุปกรณ์พิเศษ / มูลค่าสูง]"| RESERVE
        end
    end

    %% Actor Generalization (Left)
    STUDENT["🧑‍🎓 Student<br/>(นักศึกษา)"] -->|is-a| MEMBER["👤 Member<br/>(สมาชิก)"]
    STAFF_MEM["👨‍🏫 Staff<br/>(บุคลากร)"] -->|is-a| MEMBER

    %% Supporting Actor (Right)
    OFFICER["👨‍🔬 Lab Officer<br/>(เจ้าหน้าที่ห้องปฏิบัติการ)"]

    %% Associations
    MEMBER --- LOGIN
    MEMBER --- SEARCH
    MEMBER --- VIEW
    MEMBER --- CHECK
    MEMBER --- RESERVE

    APPROVAL --- OFFICER

    style Boundary fill:#ffffff,stroke:#37474f,stroke-width:2px
    style Core_Reservation fill:#fff9fa,stroke:#c2185b,stroke-dasharray: 4 4
    style MEMBER fill:#e3f2fd,stroke:#1565c0,stroke-width:2.5px
    style OFFICER fill:#fff7ed,stroke:#ea580c,stroke-width:2.5px
    style RESERVE fill:#fce4ec,stroke:#c2185b,stroke-width:2px
```

---

## 10. Key Takeaways, กระบวนการวิเคราะห์ 5 ขั้นตอน และ 4 คำถามชวนคิด

### 10.1 สรุป 3 แนวคิดสำคัญที่ต้องจำให้แม่น
1. **`<<include>>` (พฤติกรรมบังคับทำเสมอ 100%):**
   * *ตัวอย่าง:* `Reserve Equipment` ➔ `Check Equipment Availability`, `Verify Member Permission`
   * *คีย์เวิร์ด:* "งานหลักจะสำเร็จไม่ได้ หากไม่มีพฤติกรรมนี้"
2. **`<<extend>>` (พฤติกรรมเพิ่มเติมตามเงื่อนไขเฉพาะ):**
   * *ตัวอย่าง:* `Request Special Approval` ➔ `Reserve Equipment` `[Special Equipment]`
   * *คีย์เวิร์ด:* "เกิดขึ้นเฉพาะบางสถานการณ์ และต้องมีเงื่อนไข `[condition]` กำกับเสมอ"
3. **`Generalization / Specialization` (ความสัมพันธ์แบบ is-a):**
   * *ตัวอย่าง Actor:* `Student is-a Member`, `Staff is-a Member`
   * *ตัวอย่าง Use Case:* `Login with University SSO is a kind of Login`
   * *คีย์เวิร์ด:* "เป้าหมายเดียวกันแต่มีหลายวิธีดำเนินงาน ใช้ลูกศรหัวสามเหลี่ยมโปร่ง (△)"

---

### 10.2 กระบวนการวิเคราะห์ 5 ขั้นตอนสู่ไดอะแกรมคุณภาพ
```text
[1. Requirements]  ➜ ทำความเข้าใจความต้องการและเงื่อนไขของระบบ
       ↓
[2. Actors]        ➜ ระบุผู้ใช้ทั้งหมด และวิเคราะห์ Actor Generalization
       ↓
[3. Use Cases]     ➜ กำหนด Goal ของผู้ใช้ (Verb + Object ห้ามย่อ!)
       ↓
[4. Relationships] ➜ วิเคราะห์ include, extend, และ generalization
       ↓
[5. Use Case Dia]  ➜ วาดแผนภาพที่ชัดเจน ถูกหลัก UML และตรวจสอบเส้นความสัมพันธ์
```

---

### 10.3 4 คำถามชวนคิดสำหรับตรวจสอบความถูกต้องก่อนส่งงาน
> [!TIP] 4 คำถามตรวจสอบความถูกต้อง:
> 1. **อะไรคือพฤติกรรมที่ต้องเกิดทุกครั้ง?** ➔ คำตอบคือ `<<include>>` (พุ่งจาก Base ➔ Included)
> 2. **อะไรคือพฤติกรรมที่เกิดเฉพาะบางเงื่อนไข?** ➔ คำตอบคือ `<<extend>>` (พุ่งจาก Extension ➔ Base พร้อม `[condition]`)
> 3. **Actor ใดมีความสัมพันธ์แบบ is-a หรือใช้สิทธิ์ร่วมกัน?** ➔ คำตอบคือ `Actor Generalization` (พุ่งจาก Sub ➔ Super ด้วย △)
> 4. **Use Case ใดมีเป้าหมายเดียวกันแต่มีหลายวิธีดำเนินการ?** ➔ คำตอบคือ `Use Case Generalization` (พุ่งจาก Sub ➔ Super ด้วย △)

### 10.4 ประเด็นชวนคิดระดับเซียน: ทำไม User จึงสามารถ `Check Equipment Availability` ได้โดยตรง? (Dual-Role Use Case)

> [!NOTE] 💡 ทำไม Use Case ตัวเดียวกันถึงมีทั้งเส้น Association ตรงจาก User และเส้น `<<include>>` จาก Base Case?
> 1. **ในมุมมองของผู้ใช้ (Requirement ข้อ 3 - Standalone Inquiry):** สมาชิกต้องการเพียงแค่ค้นหาและกดดูสถานะความพร้อมของอุปกรณ์ (เช่น เช็กปฏิทินดูว่ากล้อง DSLR หรือเครื่องมือวัดว่างในวันศุกร์นี้หรือไม่) โดยที่ยังไม่ต้องจอง การทำงานนี้จึงเป็น Use Case อิสระที่มี Actor เริ่มต้นกระทำโดยตรง (`Member ── Check Equipment Availability`)
> 2. **ในมุมมองของระบบการจอง (Requirement ข้อ 4 - Mandatory Verification):** เมื่อสมาชิกตัดสินใจทำรายการจอง (`Reserve Equipment`) ระบบจะปล่อยให้การจองสำเร็จไม่ได้หากยังไม่ได้ตรวจความพร้อมซ้ำเพื่อป้องกันการจองชนเวลา (Double Booking) ระบบจึงต้องสั่งรัน `Check Equipment Availability` เสมอ 100% ผ่านความสัมพันธ์ `<<include>>`
> 3. **มาตรฐาน UML (OMG Standard):** Use Case ที่ถูก `<<include>>` **ไม่จำเป็นต้องเป็น Use Case ลับ/ปิดกั้น** สามารถเป็น Use Case ปกติที่ Actor เรียกใช้เองได้ และ Use Case อื่นก็ดึงไปรียูส (Reuse) ได้เช่นกัน นี่คือหลักการสูงสุดของการออกแบบเชิงวัตถุและ Use Case Modeling!

---

## 🔗 เอกสารที่เกี่ยวข้อง
- 📘 [[05_Case_Study_2_University_Registration|เวิร์กช็อปก่อนหน้า: ระบบลงทะเบียนเรียน (University Course Registration)]]
- 📚 [[05_Case_Study_1_Library_System|เวิร์กช็อปพื้นฐาน: ระบบห้องสมุด (Library System)]]
- 🎓 [[05_Use_Case_Diagrams|Lecture 4: สรุปทฤษฎี Use Case Diagram ฉบับเต็ม]]
- 🌐 [[Software Engineering Index|กลับสู่หน้ารวมดัชนี Software Engineering Wiki]]
