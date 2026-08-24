# IIT Indore Placement Database System (DBIS Minor Project)

A relational database system built using MySQL/MariaDB to model and automate the campus placement pipeline at IIT Indore. This project manages relational workflows spanning student records, department details, recruiting companies, placement drives, eligibility criteria, applications, multi-round selection processes, and final offer letters.

---

## Features & Highlights

* **Complete Relational Schema**: Includes 10 interconnecting tables designed with strict integrity constraints (`FOREIGN KEY`, `CASCADE`/`SET NULL` rules, and `CHECK` logic).
* **Realistic Campus Data Generation**: Pre-loaded with synthetic data reflecting IIT Indore's student distribution across key branches (CSE, EE, Mechanical, Civil, and Mathematics & Computing).
* **Data-Driven Workflow**: Simulates real-world recruitment logic where applications, multi-stage selection rounds (Aptitude, GD, Technical, HR), and offers are contingent on specific company eligibility rules (min CGPA, backlog limits, branch restrictions).
* **Idempotent Setup**: Includes wrapper scripts to clear existing tables safely and initialize/re-run setups seamlessly.

---

## Database Schema Overview

The database contains the following 10 relational entities:

| Table | Description |
| :--- | :--- |
| **`Department`** | Tracks academic branches, department codes, HOD names, and total enrollment count. |
| **`Placement_Officer`** | Stores contact details and designations of placement cell coordinators. |
| **`Company`** | Stores recruiting company details, industry type, and HR contacts. |
| **`Student`** | Contains student academic records, CGPA, backlogs, percentages, and department mapping. |
| **`Placement_Drive`** | Details job profiles, offered CTC/stipend, vacancies, drive modes, and drive dates. |
| **`Eligibility_Criteria`** | Stores drive-specific requirements (min CGPA, max backlogs, eligible branches). |
| **`Application`** | Maps student applications to drives along with real-time status tracking. |
| **`Selection_Round`** | Tracks sequential selection rounds (Aptitude, Technical, HR, etc.) for each drive. |
| **`Round_Result`** | Stores candidate scores, pass/fail status, and reviewer remarks per round. |
| **`Offer`** | Stores official offer letters extended to candidates, tracking acceptance status. |

---

## Getting Started

### Prerequisites
* **MySQL** (v8.0.16 or higher recommended for full `CHECK` constraint enforcement) or **MariaDB**.
* MySQL CLI or a client tool like MySQL Workbench / DBeaver.

### Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/BhuvaneeshVijayvargiya/DBIS-Minor-Project.git](https://github.com/BhuvaneeshVijayvargiya/DBIS-Minor-Project.git)
   cd DBIS-Minor-Project
