# Day 7 — SQL Tax Lab: Notes, Sample Data, and Relational Tables

## Date

Monday, June 1

## Project Context

This lab continues my SQL tax department practice inside Kali Linux using MariaDB. Day 6 focused on rebuilding the lab environment. Day 7 focused on actually working inside the database like an analyst: viewing data, leaving notes, checking sample records, testing filters, and confirming related tables.

The goal was not only to create tables. The goal was to slow down, inspect the data, and practice the habits used in real data work.

## Lab Environment

- **Operating system:** Kali Linux
- **Terminal:** Konsole split view
- **Database:** MariaDB
- **Database name:** `tax_lab`
- **Main table:** `tax_dept`
- **Related tables:** `tax_projects`, `tax_training`

## What I Practiced

- Viewing sample data from a larger table
- Using split view to work across terminal panes
- Leaving notes/comments in the SQL workflow
- Selecting specific columns instead of dumping every field
- Filtering records with `WHERE`
- Searching by phone number
- Previewing rows with `LIMIT`
- Confirming multiple tables exist
- Viewing sample records from related tables
- Running into syntax and column-name errors, then correcting them

## Tables Confirmed

I confirmed the database had multiple tables:

```sql
SHOW TABLES;
```

Tables:

```text
tax_dept
tax_projects
tax_training
```

This moved the lab beyond a single-table exercise and closer to relational database practice.

## Main Table: tax_dept

The main table contains sample employee data for a tax department style dataset.

Fields visible in the lab included:

```text
dept_id
first_name
last_name
job_title
tax_area
email
phone
hire_date
status
created_at
```

I viewed the table with:

```sql
SELECT * FROM tax_dept;
```

This helped confirm that the generated sample data loaded correctly.

## Viewing Specific Columns

Instead of always using `SELECT *`, I practiced narrowing the output to specific fields:

```sql
SELECT first_name, last_name, job_title
FROM tax_dept;
```

This is a better analyst habit because it makes results easier to read.

## Filtering by Phone Number

I practiced finding one employee by phone number:

```sql
SELECT first_name, last_name, job_title
FROM tax_dept
WHERE phone = '555-100-0057';
```

Result:

```text
Pamela Bell — Tax Manager
```

This showed that I could locate one specific record from the larger dataset.

## Previewing Sample Data With LIMIT

I used `LIMIT` to view smaller sections of data:

```sql
SELECT *
FROM tax_dept
LIMIT 3;
```

This is useful when a table has many rows and I do not want the terminal flooded with output.

## Related Table: tax_projects

I viewed sample data from the project table:

```sql
SELECT *
FROM tax_projects
LIMIT 6;
```

The table included project-style fields such as:

```text
project_id
dept_id
project_name
project_type
priority
start_date
due_date
project_status
notes
created_at
```

This table starts to connect department employees or departments to project work.

## Related Table: tax_training

I also viewed sample data from the training table:

```sql
SELECT *
FROM tax_training
LIMIT 9;
```

The table included training-style fields such as:

```text
training_id
dept_id
training_name
training_type
completion_date
expiration_date
score
training_status
created_at
```

This gives the lab another realistic data angle: employee training, completion status, scores, and expirations.

## Mistakes and Corrections

I hit errors while typing commands and using column names.

Examples included:

- Syntax errors from incomplete or incorrect SQL formatting
- Column-name mistakes such as referencing a column that did not exist
- Learning to check actual table fields before writing queries

The fix was to slow down and verify table structure before querying.

Useful command:

```sql
DESCRIBE tax_dept;
```

## Analyst Habit Built Today

The biggest habit built today was this:

> Do not just create data. Inspect it, filter it, sample it, and document what the output means.

This is important because real data analysis is not only about writing commands. It is about asking better questions of the data.

## What I Learned

1. Split view makes SQL practice easier because I can keep reference output visible while testing queries.
2. Comments and notes help me remember what I was trying to do.
3. `SELECT *` is useful at first, but selecting specific columns is cleaner.
4. `LIMIT` helps preview data without flooding the terminal.
5. `WHERE` lets me locate specific records.
6. Related tables make the lab more realistic.
7. Errors are easier to fix when I check the schema first.

## Current Progress

Completed today:

- Viewed the main `tax_dept` sample data
- Practiced selecting specific fields
- Filtered an employee by phone number
- Confirmed related tables exist
- Viewed sample project records
- Viewed sample training records
- Practiced working with a multi-table dataset

## Next Steps

- Practice `COUNT()` queries
- Practice `GROUP BY tax_area`
- Practice filtering active vs inactive employees
- Practice joining `tax_dept` to `tax_projects`
- Practice joining `tax_dept` to `tax_training`
- Write short findings after each query

## Portfolio Value

This lab shows a move from setup work into analysis habits. The value is not just that tables exist. The value is learning to explore data, check results, isolate records, and build toward relational queries.

Day 6 was rebuilding the lab.

Day 7 was learning how to work inside the data.
