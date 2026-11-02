# FinTrack: Expense Tracker REST API

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-Backend-brightgreen)
![MySQL](https://img.shields.io/badge/MySQL-Database-blue)
![Maven](https://img.shields.io/badge/Build-Maven-red)

FinTrack is a backend application for personal finance management, built with **Java 17, Spring Boot, Spring Data JPA and MySQL**. It exposes REST APIs to manage users, income and expense categories, and transactions, and it calculates a financial summary (total income, total expenses and current balance).

---

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Data Model](#data-model)
- [API Reference](#api-reference)
- [Getting Started](#getting-started)
- [API Testing](#api-testing)
- [Future Enhancements](#future-enhancements)
- [Author](#author)

---

## Features

- **User registration and login:** basic signup and login APIs.
- **Category management:** create, view, update and delete custom income and expense categories.
- **Transaction tracking:** add, update, view and delete user-specific transactions.
- **Financial summary:** total income, total expenses and current balance.
- **Layered REST architecture:** Controller, Service and Repository layers with Spring Data JPA/Hibernate for persistence and input validation.

## Tech Stack

| Technology | Purpose |
|---|---|
| Java 17 | Programming language |
| Spring Boot | Application framework |
| Spring Data JPA, Hibernate | Persistence and ORM |
| MySQL | Relational database |
| Maven | Build and dependency management |
| Postman | API testing |
| IntelliJ IDEA, Git, GitHub | Development and version control |

## Architecture

```text
Client (Postman) → Controller → Service → Repository → JPA / Hibernate → MySQL
```

| Layer | Responsibility |
|---|---|
| Controller | Handles HTTP requests and responses |
| Service | Business logic and validation |
| Repository | Database access through Spring Data JPA |

## Data Model

```text
User (1) ─── (N) Transaction (N) ─── (1) Category
```

| Entity | Fields |
|---|---|
| **User** | `id` (PK), `name`, `email`, `password` |
| **Category** | `id` (PK), `name`, `description` |
| **Transaction** | `id` (PK), `amount`, `type` (INCOME / EXPENSE), `description`, `transactionDate`, `userId` (FK), `categoryId` (FK) |

## API Reference

**Base URL:** `http://localhost:8082`

### Authentication and Users

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/signup` | Register a new user |
| POST | `/api/auth/login` | Log in an existing user |
| GET | `/api/users/profile` | Get user profile |

### Categories

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/categories` | Get all categories |
| POST | `/api/categories` | Create a category |
| PUT | `/api/categories/{id}` | Update a category |
| DELETE | `/api/categories/{id}` | Delete a category |

### Transactions

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/transactions` | Get all transactions |
| GET | `/api/transactions/{id}` | Get a transaction by ID |
| POST | `/api/transactions` | Create a transaction |
| PUT | `/api/transactions/{id}` | Update a transaction |
| DELETE | `/api/transactions/{id}` | Delete a transaction |

### Sample Request

`POST /api/transactions`

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

## Getting Started

### Prerequisites

- JDK 17 or higher
- Maven
- MySQL Server

### 1. Clone the repository

```bash
git clone https://github.com/vutladhanush/Finance-Tracker-API.git
cd Finance-Tracker-API
```

### 2. Create the database

```sql
CREATE DATABASE fintrack;
```

### 3. Configure database credentials

Update `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/fintrack
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD
```

> Never commit real credentials. Replace them with placeholders before pushing, or read them from environment variables.

### 4. Run the application

```bash
mvn spring-boot:run
```

The API runs at **http://localhost:8082**.

## API Testing

Test the APIs with Postman in this order:

1. `POST /api/auth/signup` to register a user.
2. `POST /api/auth/login` to log in.
3. `POST /api/categories` to create income and expense categories.
4. `POST /api/transactions` to add transactions.
5. `GET /api/transactions` to view them.

<!-- Add Postman screenshots here after you take them:
![Create Transaction](screenshots/postman-create-transaction.png)
![Get Transactions](screenshots/postman-get-transactions.png)
-->

## Future Enhancements

- Password hashing (BCrypt) and JWT-based authentication with Spring Security
- Pagination and filtering of transactions by date, type and category
- Monthly and category-wise reports
- Swagger / OpenAPI documentation
- Unit and integration tests with JUnit and Mockito
- Docker setup

## Author

**Dhanush Vutla**
B.Tech, Computer Science and Engineering, KL University
GitHub: [github.com/vutladhanush](https://github.com/vutladhanush)
