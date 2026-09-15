---
tags:
  - software-engineering
  - workshops
  - use-case
  - atm
  - elevator
created: 2026-09-08
updated: 2026-09-08
type: workshop-guide
---

# 🛠️ เวิร์กช็อป Use Case: ระบบ ATM และระบบลิฟต์ (ATM & Elevator System)

> [!INFO] 🏷️ ข้อมูลเวิร์กช็อป
> - **โฟลเดอร์งานต้นฉบับ:** `04_Work_and_Homework/Workshop _ Write use case diagram for ATM and Elevator system_/`
> - **หมวดหมู่:** 🔧 เวิร์กช็อปภาคปฏิบัติ (Work & Workshops)

---

## 1. กรณีศึกษาระบบตู้ ATM

### 1.1 แผนภาพและ Actors
* **Actors:**
  * `Customer` (ผู้ถือบัตร / ลูกค้าธนาคาร)
  * `Bank / Central Computer` (เซิร์ฟเวอร์ธนาคาร)
  * `Technician / Maintenance Operator` (ช่างเทคนิคซ่อมบำรุง)

### 1.2 Use Cases หลัก
1. `Authenticate Customer (Verify PIN)`
2. `Withdraw Cash` ──[«include»]──> `Authenticate Customer`
3. `Deposit Funds` ──[«include»]──> `Authenticate Customer`
4. `Check Balance` ──[«include»]──> `Authenticate Customer`
5. `Print Receipt` <──[«extend»]── `Withdraw Cash` (เลือกพิมพ์หรือไม่พิมพ์ก็ได้)
6. `Replenish Cash / Maintenance` (เชื่อมกับ `Technician`)

---

## 2. กรณีศึกษาระบบลิฟต์ (Elevator Control System)

### 2.1 Actors และความสัมพันธ์
* **Actors:**
  * `Passenger` (ผู้โดยสาร)
  * `Fire Safety System` (ระบบตรวจจับอัคคีภัย)
  * `Maintenance Operator` (ช่างซ่อมบำรุง)

### 2.2 Use Cases หลัก
1. `Call Elevator (Request Pick-up)` — กดปุ่มเรียกลิฟต์จากภายนอก
2. `Select Destination Floor` — กดเลือกชั้นปลายทางภายในลิฟต์
3. `Open / Close Doors`
4. `Emergency Stop / Alarm` <──[«extend»]── `Operate Elevator`
5. `Fire Emergency Override` — เมื่อตรวจพบควัน ลิฟต์จะลงจอดชั้น 1 และเปิดประตูค้างอัตโนมัติ
