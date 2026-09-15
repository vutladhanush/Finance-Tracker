# FinTrack - Expense Tracker

FinTrack is a full-stack Expense Tracker application built using Java Spring Boot and React.js.

The application allows users to manage their income, expenses, categories, and financial transactions through a simple and user-friendly interface.
## Features

- User Signup and Login
- JWT-based Authentication
- BCrypt Password Encryption
- Add Income Transactions
- Add Expense Transactions
- Create and Manage Categories
- View Transaction History
- Update Transactions
- Delete Transactions
- Track Total Income
- Track Total Expenses
- Calculate Current Balance
- User-specific Transactions
- RESTful APIs
- MySQL Database
- Input Validation
## Application Screenshots

### Home Page

![FinTrack Home Page](screenshots/home-page.png)

### Login Page

![FinTrack Login Page](screenshots/login-page.png)

### Signup Page

![FinTrack Signup Page](screenshots/signup-page.png)

### Dashboard

![FinTrack Dashboard](screenshots/dashboard.png)

### API Testing

![Postman API Testing](screenshots/postman.png)

## Tech Stack

### Backend

- Java
- Spring Boot
- Spring Security
- Spring Data JPA
- Hibernate
- JWT Authentication
- BCrypt
- Maven
- MySQL

### Frontend

- React.js
- JavaScript
- HTML
- CSS
- Vite
- Lucide React

### Tools

- IntelliJ IDEA
- Visual Studio Code
- Postman
- Git
- GitHub

Yes — this is correct. ✅

Add exactly this as **Section 5 — Application Architecture** in your `README.md`.

One small improvement: your architecture diagram doesn't explicitly show the **Entity Layer**, even though you explain it below. That's okay, but for consistency I recommend this version:

 
## Application Architecture

The application follows a layered architecture in the Spring Boot backend.

 
React.js Frontend
        |
        | HTTP / JSON
        ↓
Spring Boot REST API
        |
        ↓
Controller Layer
        |
        ↓
Service Layer
        |
        ↓
Repository Layer
        |
        ↓
JPA / Hibernate
        |
        ↓
Entity Layer
        |
        ↓
MySQL Database
 

### Architecture Layers

**Controller Layer**

* Handles HTTP requests and responses
* Provides REST API endpoints
* Receives and validates client requests

**Service Layer**

* Contains business logic
* Processes application operations
* Communicates between controllers and repositories

**Repository Layer**

* Handles database operations
* Uses Spring Data JPA
* Communicates with the MySQL database

**Entity Layer**

* Represents database tables
* Defines relationships between users, categories, and transactions

**Security Layer**

* Handles user authentication
* Generates and validates JWT tokens
* Protects secured API endpoints
 

