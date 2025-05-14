
# Library Database 

This repository contains the SQL script to create a relational database schema for a library management system. The database includes tables for authors, publishers, books, members, and borrowing records.

## Database Structure

### Tables Included:
- **Authors**: Stores information about book authors.
- **Publishers**: Stores publisher details.
- **Books**: Contains book information and links to publishers.
- **Book_Authors**: Junction table for the many-to-many relationship between books and authors.
- **Members**: Contains library member information.
- **Borrowing_Records**: Tracks which members borrow which books and when.

## SQL Script

The SQL script includes:
- Database creation (`library_db`)
- Table creation with appropriate primary keys, foreign keys, and constraints

## How to Use

1. Clone this repository or copy the SQL script.
2. Run the SQL script in your MySQL or MariaDB environment.
3. Use the database for library management purposes or as a template for similar projects.

## Example Usage
```sql
-- Switch to the database
USE library_db;

-- View all books
SELECT * FROM Books;

-- Get borrowing records of a specific member
SELECT * FROM Borrowing_Records WHERE member_id = 1;
```

## License

This project is open-source and available under the MIT License.
