# 🧪 QA Portfolio — Project 2: Manual Testing

**Target:** [Swag Labs / saucedemo.com](https://www.saucedemo.com)  
**Tools:** Chrome DevTools · Google Sheets · HTML/CSS/JS  
**Type:** Manual Testing — Functional, Negative, Edge Case, Security, Performance, Visual

---

## 📌 Project Overview

โปรเจคนี้เป็น Manual Testing แบบครบวงจรสำหรับ Web Application **Swag Labs** ซึ่งเป็น e-commerce demo ที่ออกแบบมาสำหรับทดสอบ QA โดยเฉพาะ

ครอบคลุมทุก Feature ตั้งแต่ Login → Product List → Product Detail → Cart → Checkout → Logout  
และทดสอบกับ **6 user types** ที่แต่ละคนมี bug ต่างกัน

---

## 🔗 Quick Links

| Resource | Link |
|----------|------|
| 🐛 Bug Report (Interactive) | [View Live Page](https://ctrlfaith.github.io/qa-portfolio-manual-testing/) |
| 📋 Test Plan & Test Cases (Google Sheets) | [Open Sheets](https://docs.google.com/spreadsheets/d/1iFCHBdt1xipGi2chOP_mHmN_25cUc-CUQ2COYInDL94/edit?usp=sharing) |
| 📁 Test Plan (CSV) | [test-plan.csv](./test-plan.csv) |
| 📁 Test Cases (CSV) | [test-cases.csv](./test-cases.csv) |

---

## 🎯 Test Scope

### Features Tested
| Feature | TC Count | Users Tested |
|---------|----------|--------------|
| Login | 17 TCs | all users |
| Product List | 46 TCs | all 6 users |
| Product Detail | 27 TCs | all 6 users |
| Cart & Checkout | 29 TCs | all 6 users |
| Logout | 3 TCs | any user |
| **Total** | **~129 TCs** | |

### Users Tested
| User | Behavior |
|------|----------|
| `standard_user` | Normal — ใช้เป็น baseline |
| `locked_out_user` | Login ไม่ได้ |
| `problem_user` | รูปผิด, link mapping ผิด, ปุ่มพัง |
| `performance_glitch_user` | โหลดช้าผิดปกติ (~7x slower) |
| `error_user` | Sort error, ปุ่ม disabled, Checkout พัง |
| `visual_user` | UI เพี้ยน, ราคาเปลี่ยนแปลงเอง |

### Test Types Used
`Happy Path` · `Negative` · `Edge Case` · `Security` · `User-specific` · `Performance`

---

## 🐛 Bugs Found — Summary

**Total: 25 bugs**

> นับตาม root cause ไม่ใช่จำนวน TC ที่ Fail
> TC ที่ Fail ทั้งหมดมี 44 cases แต่หลาย TC เกิดจาก bug เดียวกัน
> เช่น BUG-005 ทำให้ Sort ของ problem_user Fail ทั้ง 3 option — นับเป็น 1 bug

| Severity | Count | Examples |
|----------|-------|---------|
| 🔴 Critical | 6 | Link mapping ผิด, Checkout พัง, ราคาเปลี่ยนเอง |
| 🟠 High | 10 | Performance LCP >5s, Sort ไม่ทำงาน, ปุ่มพัง |
| 🟡 Medium | 5 | About → 404, Case-sensitive login, ราคา inconsistent |
| 🟢 Low | 4 | UI เบี้ยว, Reset App State ไม่ sync real-time |

> 👉 ดูรายละเอียดทุก bug ได้ที่ [Bug Report Interactive Page](https://ctrlfaith.github.io/qa-portfolio-manual-testing/)  
> แต่ละ bug มี: Steps to Reproduce · Expected vs Actual · Severity · Related TCs

### Notable Bugs
- **BUG-017** `[Critical]` — Link mapping สินค้าผิดทั้งหมด กดสินค้า A → ไปหน้าสินค้า B
- **BUG-013** `[Critical]` — ราคาสินค้าเปลี่ยนแปลงทุกครั้งที่กด Product Detail แล้วกลับมา
- **BUG-022** `[Critical]` — กรอก Last Name แล้ว input ไปโชว์ที่ First Name แทน
- **BUG-020** `[High]` — Checkout ด้วย Cart ว่างได้ ไม่มี validation, Total: $0.00
- **BUG-025** `[High]` — visual_user Sort Price เรียงลำดับราคาไม่ถูกต้อง ไม่ว่าจะ low→high หรือ high→low

---

## 📂 Files in This Repo

```
qa-portfolio-manual-testing/
├── README.md          ← You are here
├── index.html         ← Bug Report Interactive Page (deploy via GitHub Pages)
├── test-plan.csv      ← Test Plan (scope, approach, risk, user strategy)
└── test-cases.csv     ← Test Cases TC-L-001 ~ TC-L-129
```

---

## 🛠️ Tools Used

- **Browser:** Chrome (latest)
- **DevTools:** Performance tab (LCP, INP), Network tab, Console
- **Documentation:** Google Sheets
- **Version Control:** Git & GitHub

---

## 👤 Author

**Phuriphatthanachai Rattanatham**  
GitHub: [github.com/ctrlfaith](https://github.com/ctrlfaith)

> Part of a 4-project QA Portfolio targeting QA/Software Tester positions  
> → [Project 1: API Testing](https://github.com/ctrlfaith/qa-portfolio-api-testing)
