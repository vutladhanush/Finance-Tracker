# 📊 FinTrack - Full-Stack Expense Tracker

FinTrack is a secure, full-stack Expense Tracker application built using **Java Spring Boot, React.js, and MySQL**. It allows users to easily manage income, expenses, categories, and personal transactions through a clean and responsive web interface.

---

## 🚀 Features

* **Secure Authentication:** User Signup & Login powered by JWT (JSON Web Tokens) and BCrypt password encryption.
* **Category Management:** Create, view, update, and delete custom income/expense categories.
* **Transaction Tracking:** Add, update, view, and delete user-specific transactions.
* **Financial Dashboard:** Real-time summary showing Total Income, Total Expenses, and Current Balance.
* **Robust Backend:** Data persistence via Spring Data JPA/Hibernate, strict input validation, and RESTful API architecture.

---

## 📸 Screenshots

### Home Page
![Home Page](screenshots/home-page.png)

### Login & Signup
![Login Page](screenshots/login-page.png)
![Signup Page](screenshots/signup-page.png)

### Dashboard
![Dashboard](screenshots/dashboard.png)

---

## 🛠️ Tech Stack

**Backend**
* Java & Spring Boot
* Spring Security & Spring Data JPA
* Hibernate & MySQL
* JWT (JSON Web Tokens) & BCrypt
* Apache Maven

**Frontend**
* React.js & JavaScript
* HTML5 & CSS3
* Vite (Build Tool)
* Lucide React (Icons)

**Tools Used**
* IntelliJ IDEA & VS Code
* Postman (API Testing)
* Git & GitHub

---

## 📐 Architecture & Database

### System Flow
```text
React.js (Frontend) ➔ REST APIs ➔ Controller ➔ Service ➔ Repository ➔ JPA/Hibernate ➔ MySQL (Database)
```

### Data Model
```text
User (1) ─── 👥 ─── (N) Transaction (N) ─── 🏷️ ─── (1) Category
```

* **User:** `id` (PK), `name`, `email`, `password`
* **Category:** `id` (PK), `name`, `description`
* **Transaction:** `id` (PK), `amount`, `type` (INCOME/EXPENSE), `description`, `transactionDate`, `userId` (FK), `categoryId` (FK)

---

## 🌐 API Endpoints

### 🔐 Authentication & Users

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| POST | `/api/auth/signup` | Register a new user |
| POST | `/api/auth/login` | Authenticate user & return JWT token |
| GET | `/api/users/profile` | Get logged-in user profile |

### 🏷️ Categories

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| GET | `/api/categories` | Get all categories |
| POST | `/api/categories` | Create a new category |
| PUT | `/api/categories/{id}` | Update an existing category |
| DELETE | `/api/categories/{id}` | Delete a category |

### 💳 Transactions

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| GET | `/api/transactions` | Get all transactions for the authenticated user |
| GET | `/api/transactions/{id}` | Get specific transaction details |
| POST | `/api/transactions` | Create a new transaction |
| PUT | `/api/transactions/{id}` | Update a transaction |
| DELETE | `/api/transactions/{id}` | Delete a transaction |

#### 🗒️ Example Request Body (`POST /api/transactions`)
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

## 💻 Run Locally

### 1. Prerequisites
* JDK 17 or higher
* Node.js (v18+) & npm
* MySQL Server

### 2. Database Setup
Create a MySQL database named `fintrack`:
```sql
CREATE DATABASE fintrack;
```
Update `finance-backend/src/main/resources/application.properties` with your database username and password:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/fintrack
spring.datasource.username=YOUR_MYSQL_USERNAME
spring.datasource.password=YOUR_MYSQL_PASSWORD
```

### 3. Start the Backend
```bash
cd finance-backend
mvn spring-boot:run
```
*Backend Base URL:* `http://localhost:8082`

### 4. Start the Frontend
```bash
cd frontend/finance-frontend
npm install
npm run dev
```
*Frontend Base URL:* `http://localhost:5173`

---

## 👤 Author

**Vutla Dhanush**  
🎓 B.Tech – Computer Science and Engineering  
🌐 [GitHub Profile](https://github.com/vutladhanush)
