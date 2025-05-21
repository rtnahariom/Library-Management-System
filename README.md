# Library Management System

A simple database system to track books, members, and borrowing records using MySQL.

## Features
- Track book availability
- Record member details
- Generate borrowing history reports
- Find overdue books

## How to Use
1. **Run the SQL scripts** in [SQL_Scripts/](SQL_Scripts/)
2. **Sample queries**:
```sql
-- Find overdue books
SELECT books.title, members.name 
FROM borrowing_records
JOIN books ON borrowing_records.book_id = books.book_id
JOIN members ON borrowing_records.member_id = members.member_id
WHERE return_date IS NULL AND due_date < CURDATE();
```

## Database Structure
![ER Diagram](![ER Diagram](Documentation/ER_Diagram.png))

## Setup Guide
1. Install [MySQL](https://dev.mysql.com/downloads/)
2. Create database:
```sql
CREATE DATABASE library;
USE library;
```
3. Run the `schema.sql` file

## Sample Data
Check [Sample_Data.csv](Documentation/Sample_Data.csv) for mock book/member data

## 🤝 Contributing
Open to suggestions! Create an issue or pull request.

## License
[MIT](https://choosealicense.com/licenses/mit/)
