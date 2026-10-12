# SOFTWARE REQUIREMENTS SPECIFICATION (SRS)
## Library Management System

**Version:** 1.0  
**Project Type:** Web-Based Application  
**Prepared Date:** 12 October 2026  
**Document Status:** Initial Version

---

## 1. Introduction

### 1.1 Purpose

The purpose of the Library Management System is to automate library activities such as book management, student registration, book issuing, book returns, and fine calculation.

The system reduces manual paperwork, saves time, and improves the accuracy of library operations.

### 1.2 Scope

The Library Management System is designed for colleges, schools, and other educational institutions.

The system allows librarians to manage books and student records. Students can search for books, view availability, and check their borrowing details.

The system provides a centralized database for maintaining library information.

### 1.3 Objectives

- To maintain book records digitally.
- To manage student and librarian details.
- To simplify book issuing and returning.
- To calculate overdue fines automatically.
- To search for books quickly.
- To track available and borrowed books.
- To generate useful library reports.
- To reduce errors and paperwork.

### 1.4 Definitions and Abbreviations

- **SRS:** Software Requirements Specification
- **LMS:** Library Management System
- **Admin:** Person responsible for managing the application.
- **Librarian:** Person responsible for library operations.
- **User:** Student or authorized library member.
- **CRUD:** Create, Read, Update, and Delete.
- **DBMS:** Database Management System.

---

## 2. Overall Description

### 2.1 Product Perspective

The Library Management System is a standalone web-based application that stores and processes library information in a database.

The application consists of three major components:

1. Frontend – User interface for interacting with the system.
2. Backend – Handles business logic and application processing.
3. Database – Stores books, users, borrowing records, and fines.

### 2.2 Product Functions

The major functions of the system are:

- User login and logout.
- Book addition, modification, deletion, and searching.
- Student registration and management.
- Book issuing and returning.
- Book availability tracking.
- Due-date management.
- Fine calculation for overdue books.
- Borrowing history.
- Dashboard and report generation.

### 2.3 User Classes

**Administrator**
- Manages librarian accounts.
- Controls system settings.
- Views overall library reports.

**Librarian**
- Adds and updates books.
- Registers students.
- Issues and receives books.
- Monitors overdue books and fines.

**Student**
- Logs into the system.
- Searches for books.
- Checks book availability.
- Views borrowed books and due dates.
- Checks borrowing history and fines.

### 2.4 Operating Environment

- Operating System: Windows or Linux.
- Frontend: HTML, CSS, JavaScript.
- Backend: Python with Flask.
- Database: MySQL.
- Browser: Google Chrome, Microsoft Edge, or Mozilla Firefox.
- Development Tools: Visual Studio Code and GitHub.

*These technologies are the proposed stack and can be changed according to project requirements.*

### 2.5 Design and Implementation Constraints

- Users must have valid login credentials to access protected functions.
- Only authorized users can modify library records.
- Book issuing must be restricted when no copies are available.
- The system must maintain accurate borrowing records.
- The database must prevent inconsistent transactions.
- The application requires a working database connection.

### 2.6 Assumptions and Dependencies

- The institution maintains a list of registered students.
- Librarians enter accurate book information.
- Users have access to a browser and the internet or local network.
- The database server is available while the application is running.
- Borrowing limits and fine rates are configurable by the administrator.

---

## 3. Functional Requirements

### FR-01: User Authentication

- The system shall allow authorized users to log in.
- The system shall validate usernames or email addresses and passwords.
- The system shall provide role-based access for administrators, librarians, and students.
- The system shall allow users to log out securely.
- The system shall display an appropriate error message for invalid credentials.

### FR-02: Book Management

- The librarian shall be able to add new books.
- The librarian shall be able to update book information.
- The librarian shall be able to remove book records when permitted.
- The system shall store book title, author, ISBN, category, publisher, and quantity.
- The system shall maintain the number of available copies.
- The system shall prevent duplicate ISBN entries where ISBN is used as a unique identifier.

### FR-03: Student Management

- The librarian shall be able to register new students.
- The librarian shall be able to update student information.
- The system shall maintain student ID, name, email, department, and contact details.
- The system shall allow authorized staff to view student borrowing history.

### FR-04: Book Search

- Users shall be able to search for books by title, author, ISBN, or category.
- The system shall display book details and availability.
- The system shall display a suitable message when no matching books are found.

### FR-05: Book Issuing

- The librarian shall be able to issue available books to registered students.
- The system shall record the issue date and due date.
- The system shall decrease the available-copy count after a successful issue.
- The system shall prevent issuing books when no copies are available.
- The system shall enforce borrowing limits defined by the library.

### FR-06: Book Return

- The librarian shall be able to record returned books.
- The system shall update the borrowing record with the return date.
- The system shall increase the available-copy count after a valid return.
- The system shall identify overdue returns and calculate applicable fines.

### FR-07: Fine Management

- The system shall calculate fines based on the library's configured overdue rate.
- The system shall display the outstanding fine for each borrowing record.
- The librarian shall be able to record fine payments.
- The system shall maintain payment status and payment history.

### FR-08: Dashboard and Reports

- The system shall display the total number of books.
- The system shall display the number of available and borrowed copies.
- The system shall display registered students.
- The system shall list overdue books.
- The system shall generate issue, return, and fine reports.

### FR-09: Borrowing History

- Students shall be able to view their current borrowed books.
- Students shall be able to view due dates and applicable fines.
- The system shall maintain historical borrowing and return records.

---

## 4. Non-Functional Requirements

### NFR-01: Performance

- Common searches should return results within 3 seconds under normal operating conditions.
- The system should process routine book issue and return operations efficiently.

### NFR-02: Security

- Passwords shall be stored using a secure password-hashing method.
- Role-based authorization shall protect administrative functions.
- The system shall validate user inputs.
- Database access shall use parameterized queries to reduce SQL injection risks.
- Sessions shall be managed securely.

### NFR-03: Reliability

- The system shall maintain consistent book quantities and borrowing records.
- Database transactions shall prevent partial updates during issuing and returning.
- The application shall display meaningful errors when an operation fails.

### NFR-04: Usability

- The interface shall be simple and user-friendly.
- Navigation shall be consistent across pages.
- Error messages shall explain how users can correct common mistakes.
- The application shall support common desktop and mobile screen sizes.

### NFR-05: Maintainability

- The source code shall be organized into separate modules.
- Functions shall have meaningful names and documentation.
- The application shall use version control through Git and GitHub.
- The system shall support future feature enhancements.

### NFR-06: Data Backup and Recovery

- The database shall support regular backups.
- Authorized administrators shall be able to restore data from a valid backup.
- Recovery procedures shall be documented.

### NFR-07: Compatibility

- The application shall support modern web browsers.
- The interface shall adapt to different screen sizes.

---

## 5. External Interface Requirements

### 5.1 User Interface

The application shall include the following pages:

- Login Page
- Admin Dashboard
- Librarian Dashboard
- Student Dashboard
- Book Management Page
- Student Management Page
- Book Search Page
- Issue and Return Page
- Fine Management Page
- Reports Page

### 5.2 Software Interface

The application shall communicate with a MySQL database through a backend database connector.

The frontend shall communicate with the backend through appropriate HTTP requests.

### 5.3 Hardware Interface

The application shall run on a computer or server capable of hosting the application and database. Users shall require a computer, tablet, or smartphone with a supported browser.

---

## 6. Database Requirements

The system shall maintain the following main database tables.

### 6.1 Users Table

- user_id – Primary key
- name
- email – Unique
- password_hash
- role
- status
- created_at

### 6.2 Books Table

- book_id – Primary key
- isbn – Unique where applicable
- title
- author
- category
- publisher
- total_copies
- available_copies
- created_at

### 6.3 Students Table

- student_id – Primary key
- user_id – Foreign key, if linked to a user account
- registration_number – Unique
- department
- contact_number

### 6.4 Borrowings Table

- borrowing_id – Primary key
- book_id – Foreign key
- student_id – Foreign key
- issue_date
- due_date
- return_date
- status

### 6.5 Fines Table

- fine_id – Primary key
- borrowing_id – Foreign key
- amount
- payment_status
- payment_date

### 6.6 Database Rules

- Primary keys shall uniquely identify records.
- Foreign keys shall maintain relationships between tables.
- Email addresses and student registration numbers shall be unique where required.
- Available copies shall never be negative.
- A borrowing record shall reference an existing book and student.
- Fine payments shall be linked to the appropriate borrowing record.

---

## 7. Business Rules

1. Only registered students can borrow books.
2. Only authorized librarians can issue and return books.
3. A book can be issued only when an available copy exists.
4. Every issue transaction must have an issue date and due date.
5. A returned book must have a recorded return date.
6. Overdue fines shall follow the library's configured rules.
7. A book's availability shall be updated only after a successful transaction.
8. A student cannot exceed the configured borrowing limit.
9. Deleted or inactive accounts shall not be allowed to perform unauthorized transactions.
10. Important transaction records shall be retained according to institutional policy.

---

## 8. Use Cases

### Use Case 1: Search for a Book

**Actor:** Student or Librarian

**Precondition:** The application is accessible.

**Main Flow:**
1. The user opens the book search page.
2. The user enters a title, author, ISBN, or category.
3. The system searches the database.
4. The system displays matching books and availability.

**Postcondition:** The user can view the available book information.

### Use Case 2: Issue a Book

**Actor:** Librarian

**Precondition:** The student is registered and a copy is available.

**Main Flow:**
1. The librarian selects a student.
2. The librarian selects a book.
3. The system validates borrowing eligibility and availability.
4. The system records the issue date and due date.
5. The system decreases the available-copy count.
6. The system confirms the successful issue.

**Alternative Flow:** If the student is ineligible or no copies are available, the system rejects the issue and displays a reason.

### Use Case 3: Return a Book

**Actor:** Librarian

**Precondition:** The book has an active borrowing record.

**Main Flow:**
1. The librarian finds the borrowing record.
2. The librarian records the return.
3. The system calculates any applicable overdue fine.
4. The system updates the return date and borrowing status.
5. The system increases the available-copy count.
6. The system displays the return confirmation and fine details.

---

## 9. System Workflow

1. User opens the application.
2. User logs in with valid credentials.
3. The system identifies the user's role.
4. The system displays the appropriate dashboard.
5. The user performs authorized operations.
6. The backend validates the request.
7. The database is updated when the operation succeeds.
8. The system displays the result to the user.
9. The user logs out.

---

## 10. Testing Requirements

The system shall be tested to verify that all functional and non-functional requirements are satisfied.

| Test ID | Test Scenario | Expected Result |
|---|---|---|
| TC-01 | Login with valid credentials | Login succeeds |
| TC-02 | Login with invalid credentials | Error message appears |
| TC-03 | Add a book with valid details | Book is saved |
| TC-04 | Search for an existing book | Matching results appear |
| TC-05 | Issue an available book | Issue succeeds and stock decreases |
| TC-06 | Issue a book with zero available copies | Issue is rejected |
| TC-07 | Return an issued book | Return succeeds and stock increases |
| TC-08 | Return a book after its due date | Applicable fine is calculated |
| TC-09 | Student attempts an admin-only action | Access is denied |
| TC-10 | Search for a nonexistent book | No-results message appears |

---

## 11. Future Enhancements

The following features may be added in future versions:

- Online book reservation.
- Email or SMS due-date reminders.
- Barcode or QR-code scanning.
- Digital library and e-book integration.
- Fine payment gateway integration.
- Book recommendation system.
- Advanced analytics and reporting.
- Cloud deployment and automated backups.

---

## 12. Acceptance Criteria

The project shall be considered acceptable when:

- Authorized users can log in and access the correct functions.
- Librarians can manage books and student records.
- Users can search for books and check availability.
- Book issuing and returning work correctly.
- Stock counts remain consistent.
- Applicable overdue fines are calculated correctly.
- Unauthorized actions are blocked.
- The defined test cases pass.
- The system meets the agreed performance and usability requirements.

---

## 13. Conclusion

The Library Management System provides an organized and efficient method for managing library operations. It reduces manual work, improves record accuracy, and helps students and librarians access library information easily.

This SRS document defines the functional requirements, non-functional requirements, database structure, business rules, use cases, and testing criteria required to develop the application.
