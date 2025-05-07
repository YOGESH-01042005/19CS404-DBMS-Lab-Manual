# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University 

## ER Diagram:
![DBMSworkshop](https://github.com/user-attachments/assets/497b85f1-f76a-422c-9330-cea2252a970b)

## Entities and Attributes:
```
1.Student
     Attributes:Name,Address,Age
2.Department
     Attributes:Department Name
3.Class
     Attributes:Number,CID,Major
4.Faculty
     Attributes:Faculty Name,Address
```
## Relationships and Constraints:
```
1. Enroll (between Student and Class)
Cardinality:A student can enroll in many classes (1:N from Student to Class).
            A class can have many students enrolled (M:N overall).

Participation:
     Student: Partial (not all students may enroll).
     Class: Partial (not all classes may have enrolled students)
2. Works (between Faculty and Department)
Cardinality:A faculty member works in one department (N:1 from Faculty to Department).
            A department can have many faculty members.

Participation:
     Faculty: Total (every faculty works in a department).
     Department: Partial (not every department may have faculty)
3. Belongs To (between Student and Department)
Cardinality:A student belongs to one department (N:1 from Student to Department).
            A department can have many students.

Participation:
     Student: Total (each student belongs to a department).
     Department: Partial (not all departments have students).

..
```
## Extension (Prerequisite / Billing):
Prerequisite Modeling:

The prerequisite relationship for courses is implied and can be modeled using a recursive relationship on the Course entity:

Prerequisite(course_no, prereq_course_no)

This indicates that course_no requires prereq_course_no as a prerequisite.

Both attributes are foreign keys referring to the Course table.



## Design Choices:
Entities were chosen based on the core objects needed to represent a university system: universities, departments, programs, courses, students, and enrollments.

Enrollment was created as a separate entity to capture the M:N relationship between students and courses with an extra attribute (date).

Recursive relationship for prerequisites avoids cluttering the ER diagram while still supporting required functionality.

Faculty and contact information were simplified for diagram clarity but can be extended in implementation.

## RESULT
Successfully designed and explained an ER diagram for a university database with all required entities, relationships, and constraints including support for course prerequisites.
