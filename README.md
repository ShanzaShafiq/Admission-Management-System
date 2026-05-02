# 🎓 Admission Management System
> A fully normalized relational database solution that automates university admissions — replacing manual processes with a fast, transparent digital system.

## 👩‍💻 Team
| Roll No | Name |
|---------|------|
| BITF24M008 | Shanza Shafiq |
| BITF24M016 | Aswah Rani |
| BITF24M029 | Tehreem Fatima |

> **Course:** Database Systems
>  **Supervisor:** Dr. Asif Sohail
>  **University:** PUCIT Lahore

## ⚡ What It Does
- Online application portal with real-time status tracking
- Supports **Open Merit, Self-Support & Quota** admissions (Sports, Disabled, Minority, Hafiz-e-Quran)
- **Auto merit calculation:** Matric (10%) + Inter (40%) + Entry Test (50%) + Hafiz Bonus (+20)
- Integrated **fee challan**, document verification & hostel management
- Role-based admin access with full audit trail

## 🗃️ Database at a Glance
**22 Tables · 3 Views · 2 Procedures · 2 Functions · 2 Triggers · 5 Reports**

| Layer | Tables |
|-------|--------|
| Student &admin | `STUDENT` `USER_ACCOUNT` `ADMIN` |
| University Structure | `CAMPUS` `DEPARTMENT` `PROGRAM` |
| Admission Flow | `APPLICATION` `SESSION` `ADMISSION_CATEGORY` `QUOTA` |
| Academic & Test | `ACADEMIC_MARKS` `TEST_SCORE` `HAFIZ_CERTIFICATE` `DOCUMENTS` |
| Finance | `FEE_CHALLAN` `PAYMENT` `ACCOUNTS_OFFICE` |
| Merit & Offers | `MERIT` `MERIT_LIST` `MERIT_RECORD` `ADMISSION_OFFER` `HOSTEL` |

> All tables normalized to **BCNF**. RANK removed from MERIT table (3NF violation) — computed dynamically via SQL window functions.


## 🔢 Merit Formula

Final Score = (Matric% × 0.10) + (Inter% × 0.40) + (Test% × 0.50) + HafizBonus

> Score capped at 100Hafiz bonus = +20 (after admin verification)


## 🛠️ PL/SQL Implementation
Sql
--Calculate merit for any application
SELECT CALCULATE_FINAL_MERIT('APP20240001') FROM DUAL;  -- Returns: 87.02

-Check seat availability
SELECT CHECK_SEAT_AVAILABILITY('PROG001', 'CAT001') FROM DUAL;

-View active applications
SELECT * FROM ACTIVE_APPLICATIONS;


*Academic Project · PUCIT Lahore · 2024*
