# 🏥 Medical Data History – SQL Project

A relational database project based on real-world medical records including **patients, doctors, admissions, and provinces**, containing 34 SQL tasks covering **DDL, DML, Joins, Aggregate functions, String functions, Window logic, GROUP BY, HAVING, CASE, etc.**

This project was completed during my **internship at Datamites** as part of practical database handling and SQL query development learning.

---

## 📁 Project Structure

Medical-Data-History/
│── admissions.csv
│── doctors.csv
│── patients.csv
│── province_names.csv
│── Medical_Data_History.sql
│── Medical Data History.docx
│── README.md

pgsql
Copy code

---

## 📝 Project Objectives

- Study medical-record datasets and build SQL based insights.
- Perform querying operations on patient & doctor data.
- Solve 34 business problem queries.
- Apply **Joins, Aggregations, Conditions, Grouping, Filtering, CASE logic, ORDER BY, HAVING**, etc.

---

## 🛠 Tech Stack

| Component | Used |
|---------|-------|
| Database | MySQL |
| Language | SQL |
| Files Included | CSV datasets + SQL query file |

---

## 📊 Dataset Overview

| Table | Description |
|---|---|
| `patients` | Patient personal details (name, age, height, weight, allergies, etc.) |
| `doctors` | Medical practitioners and their specialties |
| `admissions` | Diagnosis & admission history |
| `province_names` | Province/region lookup table |

---

## 🧩 ER Diagram

The Entity–Relationship (ER) diagram below shows how the tables are connected in the **Medical Data History** database.


Note: In the admissions table, the column attending_doctor_id is treated as doctor_id to join with the doctors table.

🔍 Key SQL Learning Areas
Filtering (WHERE, BETWEEN, IN, LIKE)

Aggregations (COUNT, SUM, MAX, MIN)

GROUP BY & HAVING conditions

String functions (CONCAT, UPPER, LOWER, etc.)

Joins for relational mapping

Data cleaning (NULL handling + updates)

Conditional logic using CASE

BMI & obesity classification

📌 Project Tasks Overview
All 34 SQL tasks solved inside: Medical_Data_History.sql

Example Types of Queries Solved:

Filter male patients

Handle NULL allergies

Join patients with provinces

Count admissions and group by diagnosis

Group cities by patient count

Identify obese patients using BMI

Find unique first names

Detect repeat diagnosis admissions

🏆 Sample Query Snippets
sql
Copy code
-- Highest height patient
select first_name, last_name, height 
from patients 
order by height desc 
limit 1;
sql
Copy code
-- Patients diagnosed with Dementia
select distinct p.patient_id , p.first_name , p.last_name, a.diagnosis
from patients as p 
join admissions as a 
on p.patient_id = a.patient_id 
where a.diagnosis = 'Dementia';
sql
Copy code
-- BMI-based obesity classification
select patient_id, weight, height,
case when (weight / power(height / 100, 2)) >= 30 then 1 else 0 end as isObese 
from patients;
🚀 How to Run
bash
Copy code
# 1. Create database & open MySQL
mysql -u root -p

# 2. (Optional) Create database
CREATE DATABASE project_medical_data_history;
USE project_medical_data_history;

# 3. Import SQL file
source Medical_Data_History.sql;

# 4. Load CSV Files into corresponding tables
(via MySQL Workbench or LOAD DATA INFILE)
# 🔮 Future Enhancements
Create Power BI or Tableau dashboard

Build stored procedures / triggers

Convert to mini-web app with Flask / Streamlit / Node

Add automated data validation checks

# 👨‍💻 Author
Debabrata Das
Data Analytics Intern – Datamites
