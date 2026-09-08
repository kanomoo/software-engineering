---
tags:
  - software-engineering
  - workshops
  - use-case
  - library
created: 2026-09-08
updated: 2026-09-08
type: workshop-guide
---

# 🛠️ เวิร์กช็อป Use Case: ระบบห้องสมุดกลาง (KMUTNB Central Library)

> [!INFO] 🏷️ ข้อมูลเวิร์กช็อป
> - **โฟลเดอร์งานต้นฉบับ:** `04_Work_and_Homework/Homework use case diagram _ Write a use case diagram for KMUTNB central library_/`
> - **หมวดหมู่:** 🔧 เวิร์กช็อปภาคปฏิบัติ (Work & Workshops)

---

## 1. ขอบเขตระบบห้องสมุดกลาง (System Boundary)

ระบบบริหารจัดการการยืม-คืนหนังสือ ค้นหาทรัพยากรสารสนเทศ และการชำระค่าปรับของสำนักหอสมุดกลาง

### 1.1 Actors ในระบบ
1. `Student / Member` (นักศึกษา / สมาชิกห้องสมุด)
2. `Librarian` (บรรณารักษ์ / เจ้าหน้าที่เคาน์เตอร์)
3. `Library Admin` (ผู้ดูแลระบบ)
4. `Payment Gateway` (ระบบชำระเงินค่าปรับออนไลน์)

---

## 2. แผนผัง Use Cases และความสัมพันธ์

* `Search Catalog (OPAC)` — ใครก็ค้นหาได้ ไม่จำเป็นต้องล็อกอิน
* `Borrow Books` $\xrightarrow{<<include>>}$ `Verify Member Card` และ `Check Book Status`
* `Return Books`
* `Pay Overdue Fine` $\xleftarrow{<<extend>>}$ `Return Books` (เกิดขึ้นเมื่อคืนหนังสือเกินกำหนด)
* `Reserve Book` — สมาชิกจองหนังสือที่กำลังถูกยืมอยู่
* `Manage Book Inventory` — บรรณารักษ์เพิ่ม/ลบ/แก้ไขข้อมูลหนังสือ
