# 🔐 Auth Service (Spring Boot Microservice)

A production-level **Authentication & Authorization Service** built using Spring Boot, implementing **JWT-based authentication**, **Refresh Tokens**, and **Role-Based Access Control (RBAC)**.

---

## 🚀 Overview

This service acts as a centralized **Auth microservice** responsible for:

* User Signup & Login
* JWT Access Token generation
* Refresh Token management
* Secure password storage
* Role-based authorization

It is designed to integrate with API Gateway and other microservices.

---

## 🧠 Architecture

* Stateless authentication using JWT
* Refresh tokens stored in database
* Spring Security filter-based request validation
* Scalable microservice design

---

## 🗂️ Database Design

### Tables:

* **users** → stores user credentials
* **roles** → defines roles (ADMIN, USER)
* **users_roles** → mapping table (Many-to-Many)
* **tokens** → stores refresh tokens

---

## ⚙️ Tech Stack

* Java 17+
* Spring Boot
* Spring Security
* JWT (JSON Web Token)
* MySQL / PostgreSQL
* Maven / Gradle

---

## 🔑 Features

### ✅ Authentication

* User Signup
* User Login
* Password encryption using BCrypt

### 🔐 Authorization

* Role-based access control (RBAC)

### 🔁 Token Management

* Access Token (short-lived)
* Refresh Token (long-lived)
* Token validation & regeneration

### ⚡ Security

* JWT Filter for request validation
* Secure endpoints using Spring Security

---

## 📡 API Endpoints

### 🧾 Auth APIs

| Method | Endpoint                | Description                    |
| ------ | ----------------------- | ------------------------------ |
| POST   | `/auth/v1/signup`       | Register a new user            |
| POST   | `/auth/v1/login`        | Authenticate user & get tokens |
| POST   | `/auth/v1/refreshToken` | Generate new access token      |
| GET    | `/ping`                 | Health check                   |

---

## 🔄 Flow

### 🔐 Login Flow

1. User sends credentials
2. AuthenticationManager validates
3. Access + Refresh tokens generated
4. Tokens returned to client

---

### 🔁 Refresh Token Flow

1. Client sends refresh token
2. Server validates from DB
3. New access token issued

---

### 🔍 Request Flow

1. Client sends JWT in header
2. JWTFilter intercepts request
3. Token validated
4. Request forwarded to controller

---

## 📁 Project Structure

```
auth-service/
│── controller/
│   └── AuthController.java
│
│── service/
│   ├── JwtService.java
│   ├── RefreshTokenService.java
│   └── UserDetailsServiceImpl.java
│
│── config/
│   └── SecurityConfig.java
│
│── filter/
│   └── JwtFilter.java
│
│── entity/
│   ├── User.java
│   ├── Role.java
│   └── Token.java
│
│── repository/
│
│── dto/
│
│── application.yml
```

---

## 🔐 Security Implementation

* Password hashing using BCrypt
* Stateless JWT authentication
* Refresh token validation via DB
* Secure endpoints via Spring Security

---

## ⚡ Non-Functional Requirements

* Fast authentication (minimal DB calls)
* Scalable microservice design
* Fault-tolerant token handling

---

## 🧪 Testing

Use Postman or any API client:

1. Signup a user
2. Login to get tokens
3. Use access token in headers:

   ```
   Authorization: Bearer <access_token>
   ```
4. Refresh token when access token expires

---

## 🚀 Future Improvements

* 🔥 Logout (token revocation)
* 🔥 Rate limiting (prevent brute force attacks)
* 🔥 Redis for token storage
* 🔥 Email verification
* 🔥 API Gateway integration
* 🔥 OAuth2 / Keycloak integration

---

## 📌 How to Run

```bash
# Clone repo
git clone <your-repo-url>

# Navigate
cd auth-service

# Run project
./mvnw spring-boot:run
```

---

## 🤝 Contribution

Contributions are welcome! Feel free to open issues or submit PRs.

---

## 📜 License

This project is open-source and available under the MIT License.

---

## 💡 Author

Built as part of a **microservices + backend engineering learning journey**.
