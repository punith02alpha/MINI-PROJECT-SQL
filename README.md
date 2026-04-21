Student Course Enrollment System (Mini Project)

Overview

This project is a **MySQL-based Student Course Enrollment System** that manages:

* Students
* Courses
* Enrollments
* Exams
* Results

It demonstrates relational database design using SQL.

---
Database Structure
Tables:

* `students` – student details
* `courses` – course information
* `enrollment` – student-course mapping
* `exams` – exam records
* `results` – marks and grades

---

Relationships

* Students ↔ Courses → Many-to-Many
* Students → Exams → One-to-Many
* Exams → Results → One-to-One

---

Features

* Add and manage student records
* Manage course data
* Enroll students in courses
* Store exam and result details
* Perform analytical SQL queries

---

Sample Queries

```sql
-- List all students
SELECT * FROM students;

-- Students enrolled in "Database Systems"
SELECT s.name
FROM students s
JOIN enrollment e ON s.student_id = e.student_id
JOIN courses c ON e.course_id = c.course_id
WHERE c.course_name = 'Database Systems';

-- Highest scoring student
SELECT * FROM results ORDER BY marks DESC LIMIT 1;

-- Average marks per course
SELECT course_id, AVG(marks)
FROM results
GROUP BY course_id;
```

---

How to Run

1. Import the database

```bash
mysql -u root -p < backup.sql
```

2. Use database

```sql
USE MINIPROJECT;
SHOW TABLES;
```

---

Tools & Technologies

* MySQL
* Command Prompt
* Git
* GitHub

---

Project Structure

```
MiniProject/
 ├── backup.sql
 └── README.md
```

---

Author

Punithkumar S

---

## 📌 Conclusion

This project showcases how SQL can be used to build a structured and efficient student management system with real-world relationships and queries.
