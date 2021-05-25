
# Library-Management-System

Youtube Link :- https://www.youtube.com/watch?v=bqpamkKqzPo

This is Library Management project which uses JAVA (GUI and Backend) and MYSQL (Database).

Scope and Objective of Project:-

  - The Library Management System allows the Librarian to login using a username and a password to access the system. 

  - The Librarian can perform many functions after logging into the system, such as, adding a new book, adding a new student, issuing a book, returning (accepting) a book, and view transactions (statistics about issuing and returning of books).

  - In the System, every book has an ISBN no., Name, Author, and a Price. 

  - Every student has a student ID, Name, Course, Branch, and Year.

  - While issuing a book the Librarian must enter the ISBN number of the book, the ID of the student, and the issue date. 

  - When the book is returned, student ID is entered by the Librarian to get details of the book issued, further the return date is mentioned and the book’s status is changed to returned/available.


MYSQL has been used for database in this project. It contains 4 tables :- 

 - Book : This table contains fields like ISBN, Title, Author, Quantity and Price.
    
  -	Admin: This table contains fields like User_id and Password.
    
  -	Student: This table contains fields like Student_ID, Name, Course, Branch and Year. 
  
  -	Record: This table contains fields like Return_Date, ISBN, Student_id and Issue_Date.

MYSQL setup :- 
 
Create all the tables beforehand

Creating Database

    CREATE DATABASE library_management_system;

    USE library_management_system;

Create Book Table

    CREATE TABLE Book(ISBN int primary key, Title varchar(20) not null, Author varchar(20) not null, Price int default 0, Quantity int default 0,CHECK (Price>=0),CHECK (Quantity>=0));

Create Student Table

    CREATE TABLE Student(SID int primary key, Name varchar(20) not null, Course varchar(20) not null, Branch varchar(20) not null, Email varchar(30) not null );

Create Issue_Book Table

    CREATE TABLE Issue_Book (ISBN int, SID int,IssueDate date not null, foreign key Fk1(ISBN) references Book(ISBN),foreign key Fk2(SID) references Student(SID) ); 

Create Return_Book Table

    CREATE TABLE Return_Book (SID int,ISBN int, ReturnDate date not null, foreign key Fk1(SID) references Student(SID),foreign key Fk2(ISBN) references Book(ISBN) );

Record Table

    CREATE TABLE Record (SID int, ISBN int, IssueDate date default null, ReturnDate date default null,foreign key Fk1(SID) references Student(SID), foreign key Fk2(ISBN) references Book(ISBN) ); 

One all this tables have been created, clone the project, open in netbeans, run the project.

Report has been uploaded into repository and Youtube Description, you can refer it.

Youtube Link :- https://www.youtube.com/watch?v=bqpamkKqzPo




