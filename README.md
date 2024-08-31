# Library Management System (LMS)

## Overview
The **Library Management System** is a cost-effective and efficient solution designed to manage the comprehensive functions of a library. From tracking book availability and member details to managing fines and memberships, this system is built using Microsoft SQL Server. It includes well-defined entities and attributes for the library's operations and ensures seamless relationships among them. All functionalities are meticulously implemented, utilizing SQL knowledge and executing queries with precision.

## Key Features

### For Students
- **Search Book**: Look up books by title, author, category, and publication details.
- **Issue Book**: Borrow books from the library.
- **Renew Book**: Extend the borrowing period for issued books.
- **Return Book**: Return borrowed books to the library.
- **Pay Fine**: Settle any fines for overdue books.

### For Library Staff
- **Add Book**: Add new books to the library’s catalog.
- **Delete Book**: Remove books from the system.
- **Approve Book**: Manage book approval for student requests.
- **See Member Fine**: View fines associated with members.
- **Update Book Details**: Modify book details such as edition, availability, etc.
- **All Student Functionalities**: Access and manage all functionalities available to students.

## System Requirements
1. **Unique Book IDs**: Each book is assigned a unique identification number.
2. **Book Search**: Members can search for books by title, author, category, and publication details.
3. **Multiple Authors**: Books can have multiple authors.
4. **Book Copies**: The library may own multiple copies of a single book.
5. **Borrowing Records**: Track the borrowing history of books, including dates and members involved.
6. **Member Tracking**: Library staff can monitor borrowing records, membership details, and status.
7. **Book Reservations**: Members can reserve books if all copies are currently borrowed.
8. **Fine Management**: Fines are imposed on members who fail to return books within 15 days of borrowing.

## Database Schema and SQL Scripts

### Database Creation
```sql
/* 1. Creating a new database */
CREATE DATABASE lib_mngmt_system;

USE lib_mngmt_system;
```

### Tables and Relations
- **Categories**: `tbl_category` (category_id, category_name)
- **Publishers**: `tbl_publisher` (publisher_id, publisher_name, publication_language, publication_type)
- **Locations**: `tbl_location` (location_id, shelf_no, shelf_name, floor_no)
- **Authors**: `tbl_author` (author_id, first_name, last_name)
- **Books**: `tbl_book` (book_id, isbn_code, book_title, category_id, publisher_id, publication_year, book_edition, copies_total, copies_available, location_id)
- **Book Authors**: `tbl_book_author` (book_id, author_id)
- **Member Status**: `tbl_member_status` (active_status_id, account_type, account_status, membership_start_date, membership_end_date)
- **Members**: `tbl_member` (member_id, first_name, last_name, city, mobile_no, email_id, date_of_birth, active_status_id)
- **Library Staff**: `tbl_library_staff` (issue_by_id, staff_name, staff_designation)
- **Book Issues**: `tbl_book_issue` (issue_id, book_id, member_id, issue_date, return_date, issue_status, issued_by_id)
- **Fines Due**: `tbl_fine_due` (fine_id, member_id, issue_id, fine_date, fine_total)
- **Fine Payments**: `tbl_fine_payment` (fine_payment_id, member_id, payment_date, payment_amount)
- **Book Request Status**: `tbl_book_request_status` (available_status_id, available_status, nearest_available_date)
- **Book Requests**: `tbl_book_request` (request_id, book_id, member_id, request_date, available_status_id)

### SQL Scripts
- **Insertions**: Data insertion for authors, categories, publishers, locations, books, members, staff, and transactions.

```sql
/* Sample Data Insertion */
INSERT INTO tbl_author (first_name, last_name) VALUES ('PK', 'Nag'), ('JP', 'Holman'), ...;
INSERT INTO tbl_category (category_name) VALUES ('Engineering & Technology'), ('Spiritualism'), ...;
...
```

### ER Diagram
(Include an image or a description of the ER diagram here, detailing the relationships between entities.)

## Conclusion
The **Library Management System** is an all-inclusive system that simplifies and automates the management of a library’s operations. It provides both students and staff with the necessary tools to efficiently handle book-related tasks, maintain member information, and manage fines, ensuring a streamlined library experience.

