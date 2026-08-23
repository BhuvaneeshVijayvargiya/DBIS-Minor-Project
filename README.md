# College Placement Management System — Schema Report

## What this project does
This database keeps track of everything involved in campus placements: which students exist, which companies come to recruit, what jobs they post, and how each student's application moves forward.

## The Tables

**Department** — Stores the branches in the college, like Computer Science or Mechanical. Each department has an ID (`dept_id`, a short code like `CSE`) and a name.

**Student** — Stores each student's details: their roll number (`roll_no`), name, email, which department they belong to, their CGPA, how many active backlogs they have (`back`), their graduation year, and whether they've already been placed (`is_placed`).

**Company** — Stores basic info about a recruiting company: its ID, name, and HR contact details.

**Job** — Stores a job opening posted by a company: the role title, salary (`ctc_lpa`), the minimum CGPA required, which branches are eligible, and the application deadline.

*(Two more tables, `Application` and `Interview`, complete the picture — they record which student applied to which job, and the result of each interview round.)*

## How the tables connect
Think of it like a chain:
- A **Student** belongs to one **Department**.
- A **Job** is posted by one **Company**.
- A **Student** applies to a **Job** → this creates an **Application**.
- Each **Application** can have one or more **Interview** rounds with a result.

This is why some columns are called **foreign keys** — for example, `dept_id` inside the `Student` table isn't the student's own data, it's a *link* pointing back to a row in the `Department` table. This avoids repeating the full department name for every single student.

## Why some choices were made
- **Primary Key** (e.g. `roll_no`, `company_id`) — a column that uniquely identifies each row, so no two students or companies can be confused with each other.
- **NOT NULL** — means that field can't be left empty (e.g. every student must have a name).
- **UNIQUE** — no two rows can share the same value (e.g. two students can't have the same email).
- **DEFAULT** — an automatic starting value if nothing is entered (e.g. `back` starts at 0, `is_placed` starts as false).

## In short
This schema is small enough to build and demo easily, but it still reflects a real placement process: departments organize students, companies post jobs, students apply, and applications move through interview rounds toward a final result.
