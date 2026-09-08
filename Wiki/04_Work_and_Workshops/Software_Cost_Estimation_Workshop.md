---
tags:
  - software-engineering
  - workshops
  - cost-estimation
  - cocomo
  - function-point
created: 2026-09-08
updated: 2026-09-08
type: workshop-guide
---

# 🛠️ เวิร์กช็อปการคำนวณต้นทุนซอฟต์แวร์ (Software Cost Estimation Workshop)

> [!INFO] 🏷️ ข้อมูลเวิร์กช็อป
> - **โฟลเดอร์งานต้นฉบับ:** `04_Work_and_Homework/Sw cost estimation/`
> - **หมวดหมู่:** 🔧 เวิร์กช็อปภาคปฏิบัติ (Work & Workshops)

---

## 1. การคำนวณด้วย COCOMO Model

### สูตรคำนวณพื้นฐาน (Basic COCOMO)
$$E = a \times (\text{KLOC})^b \quad [\text{Person-Months}]$$
$$D = c \times (E)^d \quad [\text{Months (Duration)}]$$

| โหมดของระบบ (System Mode) | $a$ | $b$ | $c$ | $d$ |
|:---|:---:|:---:|:---:|:---:|
| **Organic** (ระบบขนาดเล็ก ทีมคุ้นเคย) | 2.4 | 1.05 | 2.5 | 0.38 |
| **Semidetached** (ระบบความซับซ้อนปานกลาง) | 3.0 | 1.12 | 2.5 | 0.35 |
| **Embedded** (ระบบฝังตัว ข้อจำกัดสูง) | 3.6 | 1.20 | 2.5 | 0.32 |

---

## 2. การคำนวณด้วย Function Point Analysis (FPA)

### ลำดับขั้นตอนคำนวณ 4 ก้าว:
1. **คำนวณ Unadjusted Function Points (UFP):**
   $$UFP = \sum (\text{Component Count} \times \text{Weight})$$
   นับจำนวนฟังก์ชัน 5 ชนิด: EI, EO, EQ, ILF, EIF
2. **ประเมิน 14 General System Characteristics (GSC):**
   ให้คะแนน DI แต่ละข้อตั้งแต่ $0$ ถึง $5$ รวมกันได้ $\text{Total DI}$
3. **คำนวณ Value Adjustment Factor (VAF):**
   $$VAF = 0.65 + (0.01 \times \text{Total DI})$$
4. **คำนวณ Final Function Point (FP):**
   $$FP = UFP \times VAF$$
