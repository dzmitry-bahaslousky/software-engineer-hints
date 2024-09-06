Relationships between tables in a database (or associations) define how data in one table relates to data in another. The main types of relationships between tables in relational databases include:

### 1. **One-to-One**

**Description**: Each record in one table is related to **exactly one** record in another table, and vice versa.

- **Example**: Each person may have one unique passport, and each passport has only one owner.
- **How to implement**:
    - Use a **unique foreign key** in one of the tables.
    - Sometimes implemented as a combination of tables through the primary key (PK).
```sql
CREATE TABLE Person (
    person_id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Passport (
    passport_id INT PRIMARY KEY,
    person_id INT UNIQUE, -- Unique foreign key
    FOREIGN KEY (person_id) REFERENCES Person(person_id)
);
```

### 2. **One-to-Many**

**Description**: One record in the first table can be related to **many** records in the second table, but each record in the second table is related to **only one** record in the first.

- **Example**: One person can have multiple phones, but each phone belongs to only one person.
- **How to implement**: The second table contains a foreign key pointing to the first table.
```sql
CREATE TABLE Person (
    person_id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Phone (
    phone_id INT PRIMARY KEY,
    person_id INT,
    phone_number VARCHAR(20),
    FOREIGN KEY (person_id) REFERENCES Person(person_id)
);
```

### 3. **Many-to-One**

**Description**: This relationship is simply the inverse of the **One-to-Many** relationship. Multiple records in one table can be related to one record in another table.

- **Example**: Several employees can work in one department, but each employee belongs to only one department.
- **How to implement**: Similar to the **One-to-Many** relationship, foreign keys are used to indicate the relationship.
```sql
CREATE TABLE Department (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

CREATE TABLE Employee (
    employee_id INT PRIMARY KEY,
    department_id INT,
    name VARCHAR(100),
    FOREIGN KEY (department_id) REFERENCES Department(department_id)
);
```

### 4. **Many-to-Many**

**Description**: One record in the first table can be related to **multiple** records in the second table, and vice versa. To implement this relationship, an intermediate table (junction table) is typically used to store pairs of foreign keys.

- **Example**: Students can enroll in multiple courses, and each course can be attended by multiple students.
- **How to implement**: An intermediate table is used that connects the IDs from both tables.

```sql
CREATE TABLE Student (
    student_id INT PRIMARY KEY,
    name VARCHAR(100)
);

CREATE TABLE Course (
    course_id INT PRIMARY KEY,
    course_name VARCHAR(100)
);

CREATE TABLE StudentCourse (
    student_id INT,
    course_id INT,
    PRIMARY KEY (student_id, course_id),
    FOREIGN KEY (student_id) REFERENCES Student(student_id),
    FOREIGN KEY (course_id) REFERENCES Course(course_id)
);
```

### 5. **Self-Referencing Relationship**

**Description**: A table can reference itself, creating hierarchical relationships between records. This is often used to represent hierarchies such as organizational structures (one employee can manage other employees).

- **Example**: In an employee table, one employee can be a manager for other employees.
- **How to implement**: A foreign key is added that references the primary key of the same table.

```sql
CREATE TABLE Employee (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    manager_id INT,
    FOREIGN KEY (manager_id) REFERENCES Employee(employee_id)
);
```

### Conclusion:

- **One-to-One**: Strict correspondence between records in two tables.
- **One-to-Many**: One record in the first table can be associated with multiple records in the second.
- **Many-to-One**: Multiple records in one table can reference one record in another.
- **Many-to-Many**: Multiple relationships between records in two tables, implemented through an intermediate table.
- **Self-Referencing Relationship**: A table references itself, allowing the construction of hierarchies.