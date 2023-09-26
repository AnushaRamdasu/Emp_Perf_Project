<br/>
<p align="center">
  <h1 align="center">EMPLOYEE PERFORMANCE SYSTEM</h1>


<p align="center">
    A Console-Based Employee Performance  System for to keep them engaged, content and productive.
    <br/>
    <br/>
    <a href="https://github.com/DeepthiEttamsethi/Emp_Perf_Project"><strong>Explore the docs »</strong></a>
    <br/>
  </p>
</p>

## Table Of Contents

- [About the Performance  System](#about-the-project)
- [Features](#features)
  - [User Authentication](#user-section)
  - [Manager Section](#manager-section)
    - [Add Employee Details
](#employee-details)
    - [Add Evaluation Details
](#evaluation-details)
    - [Update Evaluation Details
](#updateevaluation-details)
    - [Delete Employee
](#deleteemployee-details)
    - [Delete Evaluation Details
](#delevaluation-details)
   - [Employee Section
](#employee-details)
     - [Display Employee Performance
](#dispay-empdetails)

- [Getting the project](#project-details)
  - [Prerequisites](#Prerequisites-section)
    - [Java Development Kit (JDK)
](#jdk-details)
    - [MySQL Database
](#mysql-details)
    - [MySQL JDBC Driver
](#driver-details)
    
- [Project Setup](#project-details)
  - [Clone or Download](#clone-section)
  - [Create the Database
](#database-details)
  - [Create Database Tables
](#tables-queries)
    - [Manager Login
](#Manager-queries)
    - [Employee Login
](#Manager-queries)
    - [Employee
](#employee-queries)
    - [Evaluation
](#evaluation-queries)
  - [Update Database Connection
](#update-details)
  - [ Compile and Run
](#compileandrun-details)
  - [Menu
](#menu-details)


## [About Employee Performance ](https://github.com/markdown-it/markdown-it-sub) 

The Employee Performance Management System is a console-based Java application that facilitates the tracking and management of employee performance evaluations within an organization. It allows administrators to add employee details, record evaluation data, update evaluation records, and view employee performance information.

## Features

### User Authentication
Users can log in using a username and password. The system validates the login credentials against a MySQL database.

### Manager Section
#### Add Employee Details
Administrators can add new employee information, including name, email, gender, hire date, designation, salary, and mobile number.

#### Add Evaluation Details
Administrators can record evaluation details for employees, such as evaluation date, rating, and feedback.

#### Update Evaluation Details
Administrators can update existing evaluation records, allowing changes to evaluation date, rating, and feedback.

#### Delete Employee
Administrators can remove employee records from the database based on the employee's ID.

#### Delete Evaluation Details
Administrators can delete specific evaluation records by providing the evaluation ID.

#### Logout
Users can gracefully exit the application.

### Employee Section
#### Display Employee Performance
The system allows administrators to view a list of employee performance details, including employee ID, name, email, evaluation date, rating, and feedback.

#### Logout
Users can gracefully exit the application.


## [Getting the project](https://github.com/markdown-it/markdown-it-sub) 
To get and run this project, follow these 
steps


### Prerequisites

#### Java Development Kit (JDK)

Ensure you have Java JDK (Java Development Kit) installed on your system.

#### MySQL Database:
Set up a MySQL database to store employee and evaluation data. You should have MySQL installed and running.

#### MySQL JDBC Driver:
Download and include the MySQL JDBC driver in your project.

## [Project Setup ](https://github.com/markdown-it/markdown-it-sub) 
#### Clone or Download:
Clone or download the project source code from the repository.

#### Create the Database:
Create the "empperf" database in MySQL using a tool like phpMyAdmin or the MySQL command line

    CREATE DATABASE empperf;
#### Create Database Tables:

Set up the necessary database tables using the provided SQL commands in the Java code comments.

##### Manager Login:

    CREATE TABLE MANAGER_LOGIN(USERNAME VARCHAR(255), PASSWORD VARCHAR(255));
    
##### Employee Login:
   
    CREATE TABLE EMPLOYEE_LOGIN(Id INT PRIMARY KEY AUTO_INCREMENT, USERNAME VARCHAR(255), PASSWORD VARCHAR(255));
    
##### Employee:

    CREATE TABLE Employee (
     Id INT AUTO_INCREMENT PRIMARY KEY,
     Name VARCHAR(255) NOT NULL,
     Email VARCHAR(255) NOT NULL,
     Gender VARCHAR(255) CHECK (Gender = 'Male' OR Gender = 'Female'),
     Hiredate DATETIME NOT NULL,
     Designation VARCHAR(255) NOT NULL,
     Salary FLOAT NOT NULL,ad
     Mobileno bigint NOT NULL);


##### Evaluation:

    CREATE TABLE Evaluation (
    Id INT  PRIMARY KEY,
     EvaluationDate DATE,
     Rating INT,
     Feedback varchar(255),
     FOREIGN KEY (Id) REFERENCES Employee(Id));



#### Update Database Connection:
Update the database connection details in the Java code to match your MySQL configuration:


    conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/empperf", "root", "root");

#### Compile and Run:
Compile and run the Java application to start using the Employee Performance Management System.

#### Menu:
Utilize the menu options to interact with the system, either as an administrator or employee.


This is a basic console-based application. In a production environment, you would need to enhance security, implement error handling, and potentially create a graphical user interface (GUI) for a more user-friendly experience.
