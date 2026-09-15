# FinTrack - Expense Tracker

FinTrack is a full-stack Expense Tracker application built using **Java Spring Boot, React.js, and MySQL**.

Users can manage income, expenses, categories, and transactions through a simple web application.

---

## Features

* User Signup & Login
* JWT Authentication
* BCrypt Password Encryption
* Category Management
* Income & Expense Management
* Add, Update & Delete Transactions
* Transaction History
* User-specific Transactions
* Financial Summary
* Input Validation
* RESTful APIs

---

## Screenshots

### Home Page

![Home Page](screenshots/home-page.png)

### Login

![Login Page](screenshots/login-page.png)

### Signup

![Signup Page](screenshots/signup-page.png)

### Dashboard

![Dashboard](screenshots/dashboard.png)

### Postman

![Postman](screenshots/postman.png)

---

## Tech Stack

**Backend**

* Java
* Spring Boot
* Spring Security
* Spring Data JPA
* Hibernate
* JWT
* BCrypt
* MySQL
* Maven

**Frontend**

* React.js
* JavaScript
* HTML
* CSS
* Vite
* Lucide React

**Tools**

* IntelliJ IDEA
* VS Code
* Postman
* Git
* GitHub

---

## Architecture

```text
React.js
   ↓
REST API
   ↓
Spring Boot
   ↓
Controller
   ↓
Service
   ↓
Repository
   ↓
JPA / Hibernate
   ↓
MySQL
```

---

## Modules

### Authentication

* Signup
* Login
* JWT authentication
* BCrypt password hashing

### Users

* Create users
* View users
* User-specific data

### Categories

* Create category
* View categories
* Update category
* Delete category

### Transactions

* Create transaction
* View transactions
* Update transaction
* Delete transaction
* Income / Expense tracking

### Dashboard

* Total Income
* Total Expenses
* Current Balance
* Transaction History

---

## Database

```text
User
  │
  │ 1 : N
  ↓
Transaction
  │
  │ N : 1
  ↓
Category
```

### User

* id
* name
* email
* password

### Category

* id
* name
* description

### Transaction

* id
* amount
* type
* description
* transactionDate
* userId
* categoryId

---

## API Endpoints

### Authentication

| Method | Endpoint          | Description |
| ------ | ----------------- | ----------- |
| POST   | `/api/auth/login` | Login       |

### Users

| Method | Endpoint     | Description |
| ------ | ------------ | ----------- |
| POST   | `/api/users` | Create user |
| GET    | `/api/users` | Get users   |

### Categories

| Method | Endpoint               | Description     |
| ------ | ---------------------- | --------------- |
| GET    | `/api/categories`      | Get categories  |
| POST   | `/api/categories`      | Create category |
| PUT    | `/api/categories/{id}` | Update category |
| DELETE | `/api/categories/{id}` | Delete category |

### Transactions

| Method | Endpoint                 | Description        |
| ------ | ------------------------ | ------------------ |
| GET    | `/api/transactions`      | Get transactions   |
| GET    | `/api/transactions/{id}` | Get transaction    |
| POST   | `/api/transactions`      | Create transaction |
| PUT    | `/api/transactions/{id}` | Update transaction |
| DELETE | `/api/transactions/{id}` | Delete transaction |

---

## Example Request

```json
{
  "userId": 1,
  "categoryId": 1,
  "amount": 250.00,
  "type": "EXPENSE",
  "description": "Lunch",
  "transactionDate": "2026-09-04"
}
```

---

## Run Locally

### Backend

```bash
cd finance-backend
mvn spring-boot:run
```

Backend:

```text
http://localhost:8082
```

### Frontend

```bash
cd frontend/finance-frontend
npm install
npm run dev
```

Frontend:

```text
http://localhost:5173
```

---

## Author

**Vutla Dhanush**

B.Tech – Computer Science and Engineering

[GitHub](https://github.com/vutladhanush)
