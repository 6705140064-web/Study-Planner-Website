# Database Design – Study Planner Website

## 1. Overview
The database stores student accounts (if account functionality is included) and their study tasks. The MVP can use a relational database such as SQLite or MySQL.

## 2. Entity Relationship
One student can have many tasks. Each task belongs to one student.

```text
STUDENT 1 ───────────< MANY TASKS
```

## 3. Tables

### STUDENT
| Column | Data Type | Constraints | Description |
|---|---|---|---|
| student_id | INTEGER | Primary Key, Auto Increment | Unique student ID |
| name | VARCHAR(100) | NOT NULL | Student's display name |
| email | VARCHAR(255) | UNIQUE, NOT NULL | Student email |
| password_hash | VARCHAR(255) | NOT NULL | Secure password hash; never store plain-text passwords |

### TASK
| Column | Data Type | Constraints | Description |
|---|---|---|---|
| task_id | INTEGER | Primary Key, Auto Increment | Unique task ID |
| student_id | INTEGER | Foreign Key, NOT NULL | Owner of the task |
| title | VARCHAR(150) | NOT NULL | Task or assignment title |
| description | TEXT | NULL | Additional task details |
| due_date | DATE | NULL | Task deadline |
| status | VARCHAR(20) | NOT NULL, default 'pending' | pending or completed |
| created_at | DATETIME | NOT NULL | Date and time the task was created |

## 4. Relationships
- `STUDENT.student_id` is the primary key of the STUDENT table.
- `TASK.task_id` is the primary key of the TASK table.
- `TASK.student_id` references `STUDENT.student_id`.
- The relationship is one-to-many: one student can create multiple tasks.
- If accounts are used, database queries must restrict each student to their own tasks.

## 5. Example SQL (SQLite)

```sql
PRAGMA foreign_keys = ON;

CREATE TABLE student (
    student_id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    email TEXT NOT NULL UNIQUE,
    password_hash TEXT NOT NULL
);

CREATE TABLE task (
    task_id INTEGER PRIMARY KEY AUTOINCREMENT,
    student_id INTEGER NOT NULL,
    title TEXT NOT NULL,
    description TEXT,
    due_date TEXT,
    status TEXT NOT NULL DEFAULT 'pending'
        CHECK (status IN ('pending', 'completed')),
    created_at TEXT NOT NULL DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (student_id)
        REFERENCES student(student_id)
        ON DELETE CASCADE
);

CREATE INDEX idx_task_student_due_date
ON task(student_id, due_date);
```

## 6. Design Notes
- Dates are stored in ISO format (`YYYY-MM-DD`) in SQLite.
- The status field is limited to `pending` or `completed`.
- The foreign key ensures each task is linked to a student.
- If the first prototype does not include login/accounts, the STUDENT table can be postponed and tasks can be stored locally for demonstration. The team should update this design to match the implementation.
