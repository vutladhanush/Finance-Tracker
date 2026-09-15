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

 

### 1. Authentication

The authentication module provides secure access to the application.

Features:

- User registration
- User login
- BCrypt password encryption
- JWT token generation
- JWT-based authentication
- Stateless authentication

---

### 2. User Management

The user module manages registered user information.

Features:

- Create users
- Retrieve user information
- User authentication
- User-specific data access

---

### 3. Category Management

Users can organize their transactions using different categories.

Example categories:

- Food
- Travel
- Shopping
- Salary
- Bills
- Entertainment

Operations:

- Create category
- View categories
- Update category
- Delete category

---

### 4. Transaction Management

Users can manage both income and expense transactions.

Each transaction contains:

- Amount
- Transaction type
- Description
- Transaction date
- Category
- User

Operations:

- Create transaction
- View transactions
- View transaction by ID
- Update transaction
- Delete transaction

---

### 5. Dashboard

The dashboard provides an overview of the user's financial activity.

It displays:

- Total Income
- Total Expenses
- Current Balance
- Transaction History
- Financial Summary
 
 ## Section 7 — Database Design

Add this **below the Main Modules section**:

 
## Database Design

The application uses MySQL for data persistence.

### Database Relationships

 
User
 |
 | 1 : N
 ↓
Transaction
 |
 | N : 1
 ↓
Category
 

### User

Stores registered user information.

Fields:

* `id`
* `name`
* `email`
* `password`

### Category

Stores transaction categories.

Fields:

* `id`
* `name`
* `description`

### Transaction

Stores financial transaction information.

Fields:

* `id`
* `amount`
* `type`
* `description`
* `transactionDate`
* `userId`
* `categoryId`

### Transaction Types

The application supports two transaction types:

* `INCOME`
* `EXPENSE`

 
## Authentication Flow

FinTrack uses JWT-based authentication with Spring Security.

 
User
  |
  ↓
Login
  |
  ↓
Login API
  |
  ↓
Verify Email & Password
  |
  ↓
BCrypt Password Verification
  |
  ↓
Generate JWT Token
  |
  ↓
Return JWT Token
  |
  ↓
Frontend Stores Token
  |
  ↓
Bearer Token Sent With API Requests
  |
  ↓
JWT Authentication Filter
  |
  ↓
Authenticated User
  |
  ↓
Access Protected APIs
 

### Authentication Process

1. User enters email and password.
2. Frontend sends the credentials to the login API.
3. Backend verifies the user's credentials.
4. BCrypt is used to verify the password.
5. A JWT token is generated after successful authentication.
6. The token is returned to the frontend.
7. The frontend stores the JWT token.
8. The token is sent with subsequent protected API requests.
9. Spring Security validates the JWT token.
10. Authenticated users can access protected resources.

 
 
## API Endpoints

### Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/login` | User login |

---

### Users

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/users` | Create a new user |
| GET | `/api/users` | Get users |

---

### Categories

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/categories` | Get all categories |
| POST | `/api/categories` | Create a category |
| PUT | `/api/categories/{id}` | Update a category |
| DELETE | `/api/categories/{id}` | Delete a category |

---

### Transactions

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/transactions` | Get all transactions |
| GET | `/api/transactions/{id}` | Get transaction by ID |
| POST | `/api/transactions` | Create a transaction |
| PUT | `/api/transactions/{id}` | Update a transaction |
| DELETE | `/api/transactions/{id}` | Delete a transaction |
 

## Project Structure

 
Finance-Tracker/
│
├── backend/
│   └── finance-backend/
│       ├── src/
│       │   └── main/
│       │       ├── java/
│       │       └── resources/
│       │
│       ├── pom.xml
│       └── ...
│
├── finance-frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── services/
│   │   ├── App.jsx
│   │   ├── App.css
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── ...
│
├── screenshots/
│   ├── home-page.png
│   ├── login-page.png
│   ├── signup-page.png
│   ├── dashboard.png
│   └── postman.png
│
├── .gitignore
└── README.md
