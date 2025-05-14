
# Library Database Schema

## Database Creation
```sql
CREATE DATABASE library_db;
USE library_db;
```

## Tables

### Authors Table
```sql
CREATE TABLE Authors (
    author_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    bio TEXT
);
```

### Publishers Table
```sql
CREATE TABLE Publishers (
    publisher_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    address VARCHAR(255)
);
```

### Books Table
```sql
CREATE TABLE Books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(200) NOT NULL,
    isbn VARCHAR(13) UNIQUE NOT NULL,
    publication_year YEAR,
    publisher_id INT,
    FOREIGN KEY (publisher_id) REFERENCES Publishers(publisher_id)
);
```

### Book_Authors Table (Many-to-Many Junction Table)
```sql
CREATE TABLE Book_Authors (
    book_id INT,
    author_id INT,
    PRIMARY KEY (book_id, author_id),
    FOREIGN KEY (book_id) REFERENCES Books(book_id),
    FOREIGN KEY (author_id) REFERENCES Authors(author_id)
);
```

### Members Table
```sql
CREATE TABLE Members (
    member_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    join_date DATE
);
```

### Borrowing_Records Table
```sql
CREATE TABLE Borrowing_Records (
    record_id INT AUTO_INCREMENT PRIMARY KEY,
    book_id INT,
    member_id INT,
    borrow_date DATE NOT NULL,
    return_date DATE,
    FOREIGN KEY (book_id) REFERENCES Books(book_id),
    FOREIGN KEY (member_id) REFERENCES Members(member_id)
);
```
