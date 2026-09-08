---
tags:
  - software-engineering
  - old-curriculum-classic
  - software-products
  - product-vision
  - product-manager
  - lesson-01
created: 2026-09-08
updated: 2026-09-08
curriculum: Old & Classic Textbook
type: lesson
---

# สไลด์ 01: Software Products & Product Vision

> [!INFO] 🏷️ ข้อมูลบทเรียน
> - **โฟลเดอร์สไลด์ต้นฉบับ:** `02_Old_Slides_Textbook/01_Software_Products.pdf`
> - **หมวดหมู่:** 🏛️ หลักสูตรเดิมและตำรามาตรฐาน (Old & Classic Textbook)
> - **เป้าหมาย:** 📚 ความรู้พื้นฐานวิศวกรรมผลิตภัณฑ์ซอฟต์แวร์, การเขียน Moore's Vision Template และบทบาทของ Product Manager

---

## 1. Project-Based SE vs Product Software Engineering

| มิติเปรียบเทียบ | Project-Based Software Engineering | Product Software Engineering |
|:---|:---|:---|
| **ผู้กำหนดสเปก (Who specifies)** | ลูกค้าหรือผู้ว่าจ้างเฉพาะรายตามสัญญา | บริษัทผู้พัฒนาวิเคราะห์จากความต้องการของตลาด |
| **การควบคุมทิศทาง (Control)** | ผูกมัดตามสัญญาและขอบเขตงาน (Scope) | ผู้พัฒนาตัดสินใจฟีเจอร์และ Roadmap เอง |
| **กลุ่มเป้าหมาย (Audience)** | หน่วยงานหรือองค์กรเดี่ยว | ผู้ใช้งานจำนวนมากในตลาดเปิด (Mass Market) |
| **โมเดลธุรกิจ (Business Model)** | รับจ้างผลิต จ่ายเงินตามงวดงาน | ขายลิขสิทธิ์ (License) หรือบริการรายเดือน (SaaS) |

---

## 2. แม่แบบวิสัยทัศน์ผลิตภัณฑ์ของ Moore (Moore's Product Vision Template)

วิสัยทัศน์ผลิตภัณฑ์ที่ดีควรตอบคำถามสำคัญ 6 ประการตามโครงสร้างของ Geoffrey Moore:

$$\begin{aligned}
\text{\textbf{FOR}} &\quad [\text{กลุ่มผู้ใช้งานหรือลูกค้าเป้าหมาย}] \\
\text{\textbf{WHO}} &\quad [\text{ปัญหาหรือโอกาสทางธุรกิจที่ลูกค้ากำลังเผชิญ}] \\
\text{\textbf{THE } [\text{Product Name}]} &\quad \text{is a } [\text{ประเภทของผลิตภัณฑ์}] \\
\text{\textbf{THAT}} &\quad [\text{คุณประโยชน์หลักที่ระบบมอบให้เพื่อแก้ปัญหา}] \\
\text{\textbf{UNLIKE}} &\quad [\text{คู่แข่งหลักหรือทางเลือกเดิมที่มีอยู่ในตลาด}] \\
\text{\textbf{OUR PRODUCT}} &\quad [\text{จุดเด่นและข้อแตกต่างที่เหนือกว่าอย่างชัดเจน}]
\end{aligned}$$

---

## 3. บทบาทเชิงเทคนิค 6 ด้านของ Product Manager (PM)

1. **Feature Prioritization:** จัดลำดับความสำคัญของงานใน Product Backlog ตามมูลค่าธุรกิจ
2. **Technical Debt Management:** ให้เวลาทีมพัฒนาจัดการ Refactoring และหนี้ทางเทคนิค
3. **Architecture Constraints:** ทำความเข้าใจขีดจำกัดของระบบเพื่อไม่ให้สัญญาฟีเจอร์ที่เป็นไปไม่ได้
4. **Release Management:** ประสานงานวันเวลาเปิดตัวระบบร่วมกับฝ่ายการตลาดและวิศวกรรม
5. **Telemetry & Analytics:** วิเคราะห์ข้อมูลพฤติกรรมการใช้งานจริงเพื่อปรับปรุงฟีเจอร์
6. **Engineering Alignment:** สื่อสารวิสัยทัศน์ธุรกิจให้ทีมวิศวกรเข้าใจตรงกัน
