# 🛠️ คลังสไลด์และเวิร์กช็อป Use Case Diagram ฉบับสมบูรณ์ (2568)

โฟลเดอร์นี้รวบรวมสไลด์บรรยายหลักการออกแบบและกรณีศึกษาเชิงปฏิบัติการ (Use Case Diagram Workshop & Case Studies) ฉบับปรับปรุงใหม่ล่าสุด ครอบคลุมตั้งแต่ทฤษฎีพื้นฐาน จนถึงความสัมพันธ์ขั้นสูง (`<<include>>`, `<<extend>>`, และ `Generalization / Specialization`)

---

## 📑 สารบัญไฟล์เอกสารในโฟลเดอร์นี้

| ลำดับ | ชื่อไฟล์ | จำนวนหน้า | รายละเอียดและหัวข้อสำคัญ | เอกสารสรุปใน Wiki (Lessons) |
|:---:|:---|:---:|:---|:---|
| **01** | `Use-Case-Diagram.pdf` | 32 หน้า | **คู่มือทฤษฎีและแนวคิดหลัก Use Case Modeling ฉบับสมบูรณ์:**<br/>• นิยาม, ความสำคัญ, System Boundary และ Scope Creep<br/>• การระบุ Actor (Primary/Supporting) & Use Case (Goal-oriented)<br/>• ความสัมพันธ์ทั้ง 4 รูปแบบ (Association, include, extend, generalization)<br/>• โครงสร้าง Use Case Specification & 3 เส้นทาง (Main, Alt, Exception)<br/>• เชื่อมโยงสู่ Sequence Diagram, Class Diagram, Code & Test Cases<br/>• ข้อผิดพลาดที่พบบ่อย 6 ประการ และ Case Study โรงแรม (UC-05) | [[05_Use_Case_Diagrams]] |
| **02** | `Library_Borrow_Return_System_Case_Study.pdf` | 5 หน้า | **Case Study 1: ระบบยืม-คืนหนังสือห้องสมุด (KMUTNB / General Library):**<br/>• ฝึกวิเคราะห์ Actor: Student, Librarian<br/>• ระบุ Use Case หลัก: Search, Borrow, Return, Manage<br/>• วิเคราะห์เงื่อนไขที่ต้องเกิดเสมอ: `<<include>>` Check Member Status & Check Book Availability<br/>• สรุป Use Case Diagram ที่ถูกต้องตามมาตรฐาน | [[05_Case_Study_1_Library_System]] |
| **03** | `University_Course_Registration_System_Case_Study.pdf` | 10 หน้า | **Case Study 2: ระบบลงทะเบียนเรียนออนไลน์ของมหาวิทยาลัย (Full Workshop):**<br/>• ครบทั้ง 4 ความสัมพันธ์สำคัญ: include, extend, actor & use case generalization<br/>• Actor Hierarchy: `System User` $\rightarrow$ `Student`, `Staff` $\rightarrow$ `Instructor`, `Registrar`<br/>• `<<include>>`: Enroll Course $\rightarrow$ Check Prerequisite, Check Seat Availability<br/>• `<<extend>>`: Request Seat Override [Course Full], Request Prerequisite Override<br/>• Generalization: Make Payment (Credit Card / QR), Manage Course (Open / Close) | [[05_Case_Study_2_University_Registration]] |

---

## 🧭 ลำดับขั้นตอนการเรียนรู้ที่แนะนำ (Learning Roadmap)

```text
[1] ศึกษาทฤษฎี & สถาปัตยกรรม (32 หน้า)
    Use-Case-Diagram.pdf
              ↓
[2] ทำโจทย์กรณีศึกษาที่ 1: พื้นฐาน Actor, Use Case & Include (5 หน้า)
    Library_Borrow_Return_System_Case_Study.pdf
              ↓
[3] ทำโจทย์กรณีศึกษาที่ 2: ขั้นสูง ครบทั้ง Include, Extend & Generalization (10 หน้า)
    University_Course_Registration_System_Case_Study.pdf
```

---

## 🔗 ลิงก์เชื่อมโยง Obsidian Mega-Wiki (Lessons)
- 📖 [05_Use_Case_Diagrams](../../Wiki/01_New_Wiki_68/Lessons/05_Use_Case_Diagrams.md) — บทเรียนทฤษฎีเจาะลึก 32 สไลด์อย่างละเอียด (บรรยายที่ 4)
- 📚 [05_Case_Study_1_Library_System](../../Wiki/01_New_Wiki_68/Lessons/05_Case_Study_1_Library_System.md) — กรณีศึกษาที่ 1: ระบบห้องสมุด
- 🎓 [05_Case_Study_2_University_Registration](../../Wiki/01_New_Wiki_68/Lessons/05_Case_Study_2_University_Registration.md) — กรณีศึกษาที่ 2: ระบบลงทะเบียนเรียนมหาวิทยาลัย
- 🌐 [[Software Engineering Index]] — สารบัญใหญ่ของระบบ Wiki ทั้งหมด
