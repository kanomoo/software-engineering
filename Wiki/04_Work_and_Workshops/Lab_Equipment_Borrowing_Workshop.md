---
tags:
  - software-engineering
  - workshops
  - use-case
  - lab-equipment
  - case-study-3
created: 2026-09-22
updated: 2026-09-22
type: workshop-guide
curriculum: New 2568 / Workshop Suite
aliases:
  - Lab_Equipment_Borrowing_Workshop
---

# 🔬 เวิร์กช็อป Use Case: ระบบยืม–คืนอุปกรณ์ห้องปฏิบัติการ (Lab Equipment Borrowing Workshop)

> [!INFO] 🏷️ ข้อมูลเวิร์กช็อปและโจทย์ปฏิบัติการ
> - **สไลด์ต้นฉบับ Workshop:** `04_Work_and_Homework/Use_Case_Diagram_Workshop/Lab_Equipment_Borrowing_System_Case_Study.pdf` (หรือ `casestudy-usecase.pdf`)
> - **เอกสารเฉลยละเอียดสำหรับส่งงาน:** [`04_Work_and_Homework/Use_Case_Diagram_Workshop/Lab_Equipment_Borrowing_System_Solution.md`](../../04_Work_and_Homework/Use_Case_Diagram_Workshop/Lab_Equipment_Borrowing_System_Solution.md)
> - **บทเรียน Wiki ฉบับเต็ม:** [[05_Case_Study_3_Lab_Equipment_Borrowing|Case Study 3: Laboratory Equipment Borrowing System Full Guide]]
> - **หมวดหมู่:** 🔧 เวิร์กช็อปกรณีศึกษาขั้นสูง (ครบครัน: Actor/Use Case Generalization, `<<include>>`, `<<extend>>`)

---

## 🧭 แผนภาพสรุปภาพรวม (Quick Reference Diagram)

![UML Use Case Diagram](../../04_Work_and_Homework/Use_Case_Diagram_Workshop/lab_equipment_usecase_diagram.png)

```mermaid
flowchart LR
    subgraph System ["System: University Laboratory Equipment Borrowing System"]
        direction TB

        %% Authentication Group
        subgraph Group1 ["1. Authentication (การเข้าสู่ระบบ)"]
            direction TB
            LOGIN(["Login"])
            SSO(["Login with University SSO"])
            UP(["Login with Username and Password"])
            SSO -->|is-a| LOGIN
            UP -->|is-a| LOGIN
        end

        %% Catalog & Inquiry Group
        subgraph Group1_2 ["การสืบค้นและประวัติ (Catalog & Inquiry)"]
            direction TB
            SEARCH(["Search Equipment"])
            VIEW(["View Equipment Detail"])
            HIST(["View Borrowing History"])
        end

        %% Reservation Workflow Group
        subgraph Group2 ["2. Reservation Workflow (การจองอุปกรณ์)"]
            direction TB
            RESERVE(["Reserve Equipment"])
            VER_PERM(["Verify Member Permission"])
            CHK_AVAIL(["Check Equipment Availability"])
            REQ_SPEC(["Request Special Approval"])

            RESERVE -.->|«include»| VER_PERM
            RESERVE -.->|«include»| CHK_AVAIL
            REQ_SPEC -.->|"«extend» [Special Equipment]"| RESERVE
        end

        %% Borrow Operations Group
        subgraph Group3 ["3. Borrow Operations (การยืมอุปกรณ์)"]
            direction TB
            BORROW(["Borrow Equipment"])
            VER_RES(["Verify Reservation"])
            REC_BORROW(["Record Borrowing Transaction"])

            BORROW -.->|«include»| VER_RES
            BORROW -.->|«include»| REC_BORROW
        end

        %% Return Operations Group
        subgraph Group4 ["4. Return Operations (การคืนอุปกรณ์)"]
            direction TB
            RETURN(["Return Equipment"])
            CHK_COND(["Check Equipment Condition"])
            CALC_PEN(["Calculate Penalty"])
            REP_DMG(["Report Equipment Damage"])

            RETURN -.->|«include»| CHK_COND
            CALC_PEN -.->|"«extend» [Overdue]"| RETURN
            REP_DMG -.->|"«extend» [Damaged]"| RETURN
        end

        %% Management Group
        subgraph Group5 ["5. Management & Administration (การบริหารจัดการ)"]
            direction TB
            APPROVE(["Approve Special Equipment Request"])
            MAN_EQ(["Manage Equipment"])
            MAN_USER(["Manage User Account"])
            MAN_PERM(["Manage User Permission"])
        end
    end

    %% Actor Hierarchy (Left)
    STUDENT["🧑‍🎓 Student"] -->|is-a| MEMBER["👤 Member"]
    STAFF["👨‍🏫 Staff"] -->|is-a| MEMBER

    %% Association Fan-out from Member
    MEMBER --- LOGIN
    MEMBER --- SEARCH
    MEMBER --- VIEW
    MEMBER --- CHK_AVAIL
    MEMBER --- HIST
    MEMBER --- RESERVE
    MEMBER --- BORROW
    MEMBER --- RETURN

    %% Associations to Right Actors
    APPROVE --- OFFICER["👨‍🔬 Lab Officer"]
    BORROW --- OFFICER
    RETURN --- OFFICER
    MAN_EQ --- OFFICER

    ADMIN["🛡️ Administrator"] --- MAN_USER
    ADMIN --- MAN_PERM

    style System fill:#ffffff,stroke:#0f172a,stroke-width:2.5px
    style MEMBER fill:#e0f2fe,stroke:#0284c7,stroke-width:2.5px
    style OFFICER fill:#fff7ed,stroke:#ea580c,stroke-width:2.5px
    style ADMIN fill:#f5f3ff,stroke:#7c3aed,stroke-width:2.5px
    style RESERVE fill:#fce7f3,stroke:#db2777,stroke-width:2px
    style BORROW fill:#fef08a,stroke:#ca8a04,stroke-width:2px
    style RETURN fill:#bbf7d0,stroke:#16a34a,stroke-width:2px
    style LOGIN fill:#e0f2fe,stroke:#0284c7,stroke-width:2px
```

---

## 🎯 สรุปจุดตัดคะแนนสำคัญ (Key Grading Criteria)

1. **การจำแนกประเภท Actor (Actor Generalization & Separation):**
   - มี Super Actor: `Member` (สมาชิกผู้ใช้บริการ)
   - มี Sub-Actors: `Student` และ `Staff` ที่สืบทอดมาจาก `Member` ด้วยหัวลูกศรสามเหลี่ยมโปร่ง (`is-a △`)
   - แยก **`Lab Officer`** (ผู้ปฏิบัติการห้องแล็บ) และ **`Administrator`** (ผู้ดูแลระบบ) ออกมาเป็นอิสระ ไม่ปะปนกับ `Member`
2. **การระบุ Use Case แบบ Generalization:**
   - `Login` เป็นแม่ของ `Login with University SSO` และ `Login with Username and Password`
3. **การใช้ Include อย่างแม่นยำ (สิ่งที่ต้องทำเสมอ):**
   - จอง $\rightarrow$ `Verify Member Permission` และ `Check Equipment Availability`
   - ยืม $\rightarrow$ `Verify Reservation` และ `Record Borrowing Transaction`
   - คืน $\rightarrow$ `Check Equipment Condition`
4. **การใช้ Extend พร้อม Extension Point & Guard (สิ่งที่ทำเมื่อมีเงื่อนไข):**
   - `Request Special Approval` $\rightarrow$ `Reserve Equipment` `[อุปกรณ์มูลค่าสูง / ต้องขออนุมัติพิเศษ]`
   - `Calculate Penalty` $\rightarrow$ `Return Equipment` `[คืนอุปกรณ์ล่าช้า]`
   - `Report Equipment Damage` $\rightarrow$ `Return Equipment` `[ตรวจพบอุปกรณ์เสียหาย]`
5. **การกำหนดขอบเขตระบบ (System Boundary):**
   - Use Cases ทุกตัวอยู่ในขอบเขต Actor ทุกตัวอยู่นอกขอบเขต
6. **Dual-Role Use Case (`Check Equipment Availability`):**
   - สมาชิกสามารถสืบค้นตรวจสถานะความพร้อมได้โดยตรง (`Member ── Check Equipment Availability`)
   - และในขณะเดียวกันกระบวนการจองก็บังคับทำซ้ำ 100% ผ่าน `<<include>>` จาก `Reserve Equipment` เพื่อป้องกันการจองชนเวลา

---

## 🔗 นำทางสู่บทเรียนที่เกี่ยวข้อง
- 📘 [[05_Case_Study_3_Lab_Equipment_Borrowing|อ่านบทเรียนและสเปกฉบับเต็ม]]
- 📚 [[05_Case_Study_1_Library_System|เวิร์กช็อปก่อนหน้า: Case Study 1 ระบบห้องสมุด]]
- 🎓 [[05_Case_Study_2_University_Registration|เวิร์กช็อปก่อนหน้า: Case Study 2 ระบบลงทะเบียนเรียน]]
- 🌐 [[Software Engineering Index|สารบัญใหญ่ระบบ Wiki]]
