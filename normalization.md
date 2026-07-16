# Database Normalization

**Database Normalization** is the process of organizing a database to reduce data redundancy and improve data integrity. It divides data into related tables and connects them using keys.

---

# 1. First Normal Form (1NF)

## Rule

- Each column contains only one value (atomic values).
- No repeating groups.
- Each row is unique.

### Example (Not in 1NF)

| Student_ID | Name | Subjects |
|------------|------|----------|
| 101 | Ram | Math, Science |

### After Applying 1NF

| Student_ID | Name | Subject |
|------------|------|---------|
| 101 | Ram | Math |
| 101 | Ram | Science |

---

# 2. Second Normal Form (2NF)

## Rule

- Must already be in **1NF**.
- Every non-key attribute must depend on the **entire primary key**.

### Example (Not in 2NF)

| Student_ID | Course_ID | Student_Name | Course_Name |
|------------|-----------|--------------|-------------|
| 101 | C01 | Ram | DBMS |

Here:

- **Student_Name** depends only on **Student_ID**.
- **Course_Name** depends only on **Course_ID**.

### After Applying 2NF

#### Students Table

| Student_ID | Student_Name |
|------------|--------------|
| 101 | Ram |

#### Courses Table

| Course_ID | Course_Name |
|-----------|-------------|
| C01 | DBMS |

#### Enrollment Table

| Student_ID | Course_ID |
|------------|-----------|
| 101 | C01 |

---

# 3. Third Normal Form (3NF)

## Rule

- Must already be in **2NF**.
- No transitive dependency (non-key attributes should not depend on other non-key attributes).

### Example (Not in 3NF)

| Employee_ID | Employee_Name | Department_ID | Department_Name |
|-------------|---------------|---------------|-----------------|
| E01 | Hari | D01 | Cardiology |

Here:

- **Department_Name** depends on **Department_ID**, not directly on **Employee_ID**.

### After Applying 3NF

#### Employee Table

| Employee_ID | Employee_Name | Department_ID |
|-------------|---------------|---------------|
| E01 | Hari | D01 |

#### Department Table

| Department_ID | Department_Name |
|---------------|-----------------|
| D01 | Cardiology |

---

# Benefits of Normalization

- Reduces duplicate data.
- Improves data consistency.
- Prevents update, insert, and delete anomalies.
- Makes the database easier to maintain.
- Saves storage space.