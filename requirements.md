# Library Management System – Requirements

## 1. Functional Requirements

### FR-01: User Authentication
- FR-01.1: The system shall allow registered users to log in using valid credentials.
- FR-01.2: The system shall support Administrator, Librarian, and Student roles.
- FR-01.3: The system shall enforce role-based access permissions.
- FR-01.4: The system shall display an appropriate error message for invalid login attempts.
- FR-01.5: The system shall provide a secure logout function.

### FR-02: Book Management
- FR-02.1: The system shall allow authorized librarians to add new books.
- FR-02.2: The system shall allow authorized librarians to update book details.
- FR-02.3: The system shall allow authorized personnel to deactivate eligible book records.
- FR-02.4: The system shall maintain ISBN, title, author, category, publisher, and book quantity.
- FR-02.5: The system shall validate required book information before saving.
- FR-02.6: The system shall prevent duplicate ISBN values where applicable.
- FR-02.7: The system shall maintain accurate total and available book counts.

### FR-03: Student Management
- FR-03.1: The system shall allow authorized librarians to register students.
- FR-03.2: The system shall maintain student ID, registration number, name, department, email, and account status.
- FR-03.3: The system shall prevent duplicate student registration numbers.
- FR-03.4: The system shall allow authorized personnel to update student information.
- FR-03.5: The system shall allow authorized personnel to deactivate student accounts.

### FR-04: Book Search
- FR-04.1: The system shall allow users to search for books by title, author, ISBN, or category.
- FR-04.2: The system shall display book details and current availability.
- FR-04.3: The system shall display an appropriate message when no matching books are found.
- FR-04.4: The system shall support filtering and sorting of search results.

### FR-05: Book Issuing
- FR-05.1: The system shall allow authorized librarians to issue books to eligible registered students.
- FR-05.2: The system shall verify book availability before issuing.
- FR-05.3: The system shall verify student account status and borrowing eligibility.
- FR-05.4: The system shall record the issue date and due date.
- FR-05.5: The system shall enforce the borrowing limit configured by the library.
- FR-05.6: The system shall decrease the available book count after a successful issue.
- FR-05.7: The system shall prevent issuing books when no copies are available.

### FR-06: Book Returning
- FR-06.1: The system shall allow authorized librarians to process book returns.
- FR-06.2: The system shall record the actual return date.
- FR-06.3: The system shall update the borrowing status after a successful return.
- FR-06.4: The system shall increase the available book count after a valid return.
- FR-06.5: The system shall identify overdue books.
- FR-06.6: The system shall prevent duplicate return processing.

### FR-07: Fine Management
- FR-07.1: The system shall calculate overdue fines according to the configured library policy.
- FR-07.2: The system shall display outstanding fines for applicable borrowing records.
- FR-07.3: The system shall allow authorized librarians to record fine payments.
- FR-07.4: The system shall maintain payment amount, payment date, and payment status.
- FR-07.5: The system shall prevent duplicate recording of the same payment transaction.

### FR-08: Dashboard and Reports
- FR-08.1: The system shall display total books, available copies, and borrowed copies.
- FR-08.2: The system shall display the total number of registered students.
- FR-08.3: The system shall display overdue borrowing records.
- FR-08.4: The system shall generate book issue, return, and fine reports.
- FR-08.5: The system shall allow authorized users to filter reports by date and status.

### FR-09: Borrowing History
- FR-09.1: The system shall allow students to view their currently borrowed books.
- FR-09.2: The system shall display due dates and applicable outstanding fines.
- FR-09.3: The system shall maintain historical borrowing and return records.
- FR-09.4: The system shall restrict students to viewing their own borrowing information.

## 2. Non-Functional Requirements

### NFR-01: Performance
- NFR-01.1: At least 95% of book-search requests shall complete within 3 seconds under normal test conditions.
- NFR-01.2: The system shall process book issue and return operations efficiently.

### NFR-02: Security
- NFR-02.1: The system shall store passwords using a secure, salted password-hashing algorithm.
- NFR-02.2: The system shall enforce role-based authorization for protected operations.
- NFR-02.3: The system shall use parameterized database queries to reduce SQL injection risks.
- NFR-02.4: The system shall validate user input before processing requests.
- NFR-02.5: The system shall manage user sessions securely.

### NFR-03: Reliability
- NFR-03.1: The system shall maintain consistent book inventory and borrowing records.
- NFR-03.2: Failed database operations shall not leave partially updated records.
- NFR-03.3: The system shall display meaningful error messages when operations fail.

### NFR-04: Usability
- NFR-04.1: The system shall provide a user-friendly interface with clear navigation.
- NFR-04.2: The system shall display clear validation messages and operation confirmations.
- NFR-04.3: The interface shall adapt to desktop, tablet, and mobile screen sizes.

### NFR-05: Maintainability
- NFR-05.1: The source code shall be organized into maintainable modules.
- NFR-05.2: The application shall separate presentation, business logic, and database access.
- NFR-05.3: The project shall use Git for version control and GitHub for source-code management.

### NFR-06: Data Backup and Recovery
- NFR-06.1: The system shall support regular database backups.
- NFR-06.2: The system shall provide documented procedures for restoring backed-up data.

### NFR-07: Compatibility
- NFR-07.1: The application shall support current stable versions of major web browsers.
- NFR-07.2: The application shall run in a compatible Windows or Linux environment.

## 3. Business Requirements

- BR-01: Only active, registered students shall be eligible to borrow books.
- BR-02: A book shall be issued only when an available copy exists.
- BR-03: Students shall not exceed the borrowing limit configured by the library.
- BR-04: Every borrowing record shall include an issue date and due date.
- BR-05: A return shall be processed only for an active borrowing record.
- BR-06: Overdue fines shall follow the configured library policy.
- BR-07: Available book copies shall never be negative or exceed total copies.
- BR-08: Only authorized users shall perform restricted administrative operations.
- BR-09: Historical borrowing records shall be retained according to institutional policy.
- BR-10: Book inventory and borrowing updates shall be performed consistently.

## 4. Technical Requirements

- TR-01: The frontend shall use HTML, CSS, and JavaScript.
- TR-02: The backend shall use Python with the Flask framework.
- TR-03: The database shall use MySQL.
- TR-04: The application shall use a database connector to communicate with MySQL.
- TR-05: The project shall use Git and GitHub for version control.
- TR-06: The application shall validate input on the server side.
- TR-07: The database shall enforce primary keys, foreign keys, and required uniqueness constraints.
- TR-08: The application shall use database transactions for book issuing and returning.

## 5. Acceptance Requirements

- AR-01: Users shall be able to log in and access authorized features.
- AR-02: Librarians shall be able to add, update, and manage book records.
- AR-03: Authorized users shall be able to register and manage students.
- AR-04: Users shall be able to search for books and view availability.
- AR-05: Book issuing shall correctly validate eligibility and update inventory.
- AR-06: Book returning shall correctly update borrowing records and inventory.
- AR-07: Overdue fines shall match the configured fine policy.
- AR-08: Students shall not be able to access another student's private borrowing records.
- AR-09: Reports shall reflect the corresponding database records.
- AR-10: Core functional and security test cases shall pass before release.
