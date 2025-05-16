## Relational Model in DBMS

### Introduction with a Short Story:

Imagine you're building a College Management System software. You need to manage students, teachers, courses, and marks. What would you do?

You’d store all this data in tables:

* A table for Students
* A table for Courses
* A table for Teachers

This is exactly what the Relational Model is based on — storing data in the form of **tables (relations)**.

---

### Formal Definition:

The Relational Model is a data model where data is represented in the form of tables (relations). Each table consists of **rows (tuples)** and **columns (attributes)**. This model was designed by **Dr. E.F. Codd** in 1970.

---

### Core Concepts (Explained in Detail):

#### 1. Relation (Table):

A relation means a table. It is made up of rows and columns. Each table represents a specific entity or real-world object.

**Example:**

```
Roll_No   Name    Age   Branch
101       Anush   20    CS
102       Rahul   21    IT
```

This table represents the Student entity.

#### 2. Tuple (Row):

Each row in a table is called a **tuple**. It represents a single record.

E.g., `101, Anush, 20, CS` is a tuple — complete data of one student.

#### 3. Attribute (Column):

Each column is called an **attribute**. It describes a feature or property of the entity.

E.g., Name, Age, Branch are all attributes of the Student entity.

#### 4. Domain:

Each attribute has a **domain**, which means the type or range of values it can hold.

* Age domain → 0 to 120
* Name domain → only alphabets (strings)

This helps in validating data.

#### 5. Degree and Cardinality:

* **Degree** → Number of columns (attributes) in a table.

  * If a table has 4 columns → degree = 4
* **Cardinality** → Number of rows (tuples) in a table.

  * If a table has 2 rows → cardinality = 2

#### 6. Relational Schema:

Schema defines the structure of a table including attribute names and their data types.

**Example:**

```
Student(Roll_No: int, Name: string, Age: int, Branch: string)
```

This tells us the structure of the Student table.

#### 7. Keys:

Keys are used to uniquely identify records in a table.

* **Primary Key**: Uniquely identifies each row.

  * Example: `Roll_No` in the Student table.

* **Candidate Key**: All possible unique identifiers in a table. One of them is chosen as the primary key.

* **Super Key**: Candidate key plus some extra attributes. It still uniquely identifies rows but is not minimal.

* **Foreign Key**: An attribute in one table that links to the primary key of another table.

  * Example: `Course_ID` in the Student table referring to Courses table.

#### 8. Integrity Constraints:

These rules ensure that the data in the database is accurate and consistent.

* **Entity Integrity**: Primary key can never be NULL.
* **Referential Integrity**: Foreign key must either be NULL or match a valid primary key in the referenced table.

#### 9. Operations on Relations (Relational Algebra):

Relational model supports operations to retrieve, combine, and manipulate data:

* **Select (σ)**: Filters rows
* **Project (π)**: Selects specific columns
* **Join**: Combines two tables based on a common attribute
* **Union, Intersection, Set Difference**: Performs set operations

These operations are part of **Relational Algebra**, the foundation of SQL query language.

---

### Advantages of Relational Model:

* Simple and easy to understand
* Organizes data in a structured way
* Efficient data operations
* Reduces data redundancy
* Maintains data integrity
* SQL is based on this model

---

### Real-Life Example:

Suppose you are storing college data:

**Tables:**

* `Students(Roll, Name, Age, Branch)`
* `Courses(Course_ID, Course_Name, Credits)`
* `Enrollments(Roll, Course_ID, Marks)`

This is how data is stored in the relational model — organized, efficient, and easy to manage.

---

### Short Summary in Easy Words:

Relational model means:

* Store data in tables.
* Each row is a record of an entity.
* Each column defines a feature.
* Use primary keys to uniquely identify rows.
* Use foreign keys to link related tables.
* Use relational algebra or SQL to access and manipulate data efficiently.

---

**1. Composite Key – When multiple attributes together create a unique identity**

**Definition:**
A composite key is formed by combining two or more columns to uniquely identify each row in a table.

**Story-style Example:**
Imagine you're building a table called `Student_Course_Enrollment` that stores:

* Which student took which course
* What marks they obtained

```
Student_Course_Enrollment:
+-----------+------------+-------+
| Roll_No   | Course_ID  | Marks |
+-----------+------------+-------+
| 101       | CS101      | 90    |
| 101       | MA102      | 85    |
| 102       | CS101      | 92    |
+-----------+------------+-------+
```

Here, neither `Roll_No` nor `Course_ID` is unique on its own.
But when we combine both (`Roll_No + Course_ID`), we get a unique identity.

➡️ This combination is called a **Composite Key**.

**Real-Life Analogy:**
Imagine a coaching class with 10 students in each batch. Names can repeat.
But if you mention both the student name and the class time, you can identify which "Anush" attends at which time.
That's the idea of a composite key — multiple things together make a unique one.

---

**2. Compound Key – A special type of composite key which also acts as foreign keys**

**Definition:**
A compound key is essentially a composite key where each individual part can also act as a foreign key.

That means:

* Composite key → formed using multiple columns
* Compound key → same as composite key, but each part is also a foreign key

**Example:**
Again, imagine the `Student_Course_Enrollment` table.

* `Roll_No` → foreign key from the `Student` table
* `Course_ID` → foreign key from the `Course` table

When you combine both to make a primary key in the `Enrollment` table, it's called a **Compound Key**.

➡️ So, when each part of a composite key is also a foreign key, it becomes a **Compound Key**.

**Simple Understanding:**

* Every compound key is a composite key
* But not every composite key is a compound key

---

**3. Surrogate Key – When an artificial ID is created by the system**

**Definition:**
A surrogate key is an artificial, system-generated unique ID that doesn't depend on any real-world attribute.

It has no meaning in the real world — it's just a unique number or ID used to identify rows internally.

**Example:**
You're creating a `Student` table:

```
+------------+--------+-----+--------+
| Student_ID | Name   | Age | Branch |
+------------+--------+-----+--------+
| 1          | Anush  | 20  | CSE    |
| 2          | Rohan  | 21  | IT     |
| 3          | Rahul  | 19  | ECE    |
+------------+--------+-----+--------+
```

Here, `Student_ID` is not something that exists in real life — it's auto-generated by the system.

➡️ This is a **Surrogate Key** — a new ID created purely to uniquely identify data. It has no real-world meaning.

**When do we use Surrogate Keys?**

* When real-world attributes aren't unique
* When we don't want the primary key to change in the future
* When we want a simple numeric ID for fast lookup

---

**Final Recap (Real-life Summary):**

| Key Type  | What is it?                                                  | Example                                             |
| --------- | ------------------------------------------------------------ | --------------------------------------------------- |
| Composite | Multiple attributes together make a unique key               | `Roll_No + Course_ID` to identify course enrollment |
| Compound  | Composite key where each part is also a foreign key          | `Roll_No (FK)` + `Course_ID (FK)`                   |
| Surrogate | Artificial ID created by the system, unrelated to real-world | `Student_ID = 1, 2, 3` (auto-incremented IDs)       |

**Short One-liner Summary:**

* **Composite Key:** Together make it unique
* **Compound Key:** Together make it unique + also foreign keys
* **Surrogate Key:** System-generated, no real-world connection

---

---

# Integrity Constraints – A Friendly Explanation

First, let’s understand the core idea:

**"Integrity"** means correctness, accuracy, and validity of data.
**"Constraint"** means rule or restriction.

So, **Integrity Constraints** are:

Rules that ensure the data stored in a database is valid, accurate, and meaningful, preventing incorrect or useless data from being stored.

Imagine if a student's `Roll_No` is NULL, or the same roll number appears 5 times, or a student is enrolled in a course that doesn’t even exist — is that valid data? No, right?

That’s why we apply **Integrity Constraints** — to ensure the database remains consistent and valid at all times.

---

## 3 Main Types of Integrity Constraints (in the Relational Model):

### 1. Entity Integrity Constraint:

This rule states:

> "The value of the primary key in any table must always be **unique** and **non-null**."

**Why?**
Because the **primary key** uniquely identifies each record in the table.

**Example:**
Table: `Student(Roll_No, Name, Age)`

If `Roll_No = NULL` for any student, how can the system identify that student?
If two students have `Roll_No = 101`, how will the system track their courses and marks accurately?

So, the rule is:

* Primary key cannot be NULL
* Primary key must be unique

**Conclusion:** Entity Integrity means the primary key must always be **unique** and **not null**.

---

### 2. Referential Integrity Constraint:

This one is a bit more interesting. It states:

> "If one table refers to another using a foreign key, then the value must either exist in the referenced table or be NULL."

**Example:**
You have two tables:

* `Student(Roll_No, Name, Course_ID)`
* `Course(Course_ID, Course_Name)`

Now, if the `Student` table contains `Course_ID = 'CSE101'` but that course doesn’t exist in the `Course` table —
then the system doesn’t know what course the student is enrolled in. That’s invalid.

Referential Integrity ensures that:

* The `Course_ID` in the `Student` table must exist in the `Course` table.
* If it doesn’t, it should either throw an error or be set to NULL.

**In simple words:**
Any foreign key must either:

* Refer to an existing record in the referenced table
* Or be NULL

---

### 3. Domain Integrity Constraint:

This rule says:

> "Each column in a table should only contain values from its defined domain (data type and range)."

**Example:**
Table: `Student(Name: String, Age: Integer, Email: String)`

* If you enter "twenty" in the `Age` column or `2000` in the `Name` column — that’s invalid.

Domain Integrity ensures:

* Each column only accepts data that matches its type and rules.

Like:

* `Age` must be a number
* `Email` must contain `@`
* `Name` should not contain numbers

**In essence:** Domain Integrity defines the valid type and format for each column.

---

## Optional Constraint (Advanced Understanding):

### 4. Key Constraint:

A table can have one or more **candidate keys** — any of which can uniquely identify a record.

When you choose one of them, it becomes the **primary key**.

Rules for any candidate key:

* No duplicate values allowed
* No NULL values allowed

---

## Real-Life Example – Combining All Constraints:

### Scenario:

You're designing a University Database with:

* `Student(Roll_No, Name, Age, Course_ID)`
* `Course(Course_ID, Course_Name)`

You apply these constraints:

* **Entity Integrity:** `Roll_No` is the primary key → must be unique and non-null.
* **Referential Integrity:** `Course_ID` in `Student` is a foreign key → must exist in the `Course` table.
* **Domain Integrity:** `Age` should be an integer, `Name` should contain only alphabets, `Email` should follow email format.

**What if you don’t use constraints?**

* You might insert invalid data (e.g., Age = "fifty-five", Roll\_No = NULL)
* Duplicate records may appear (e.g., multiple students with Roll\_No = 101)
* Relationships might break (e.g., a student enrolled in a non-existent course)

This leads to an **unreliable and inconsistent database system**.

That’s why constraints are essential — they act as the **moral police** of the database.

---

## Final Summary:

**Integrity Constraints** are rules that keep data valid and meaningful.

* **Entity Integrity:** Primary key must be unique and not null.
* **Referential Integrity:** Foreign key must refer to an existing record or be NULL.
* **Domain Integrity:** Each column must contain data matching its type and range.
* **Key Constraint:** Any key used to identify records must be unique and not null.

---
