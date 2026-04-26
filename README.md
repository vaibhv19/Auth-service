# 🔐 Auth Service

A centralized **Authentication & Authorization microservice** built with **Spring Boot** and **Spring Security** that handles secure user signup, login, JWT token generation, refresh token management, and role-based access control.

---

## 🚀 Overview

This project is designed to simulate a production-style auth system used in modern backend applications and microservice architectures.

It provides:

* Secure user registration and login
* JWT-based stateless authentication
* Refresh token mechanism for persistent sessions
* Role-Based Access Control (RBAC)
* Protected API endpoints using Spring Security

---

## 🛠️ Tech Stack

* Java
* Spring Boot
* Spring Security
* Spring Data JPA / Hibernate
* MySQL
* Maven / Gradle
* Postman
* Git & GitHub

---

## ✨ Features

* User Signup API
* User Login API
* JWT Access Token generation
* Refresh Token flow
* Password encryption using BCrypt
* Role-based authorization (USER / ADMIN)
* Custom JWT filter for request validation
* Protected endpoints with Spring Security

---

## 🏗️ Architecture

The project follows a **layered architecture** with clean separation of concerns:

```id="k8xv31"
src/main/java/authservice
│── controller
│── service
│── repository
│── entities
│── request
│── response
│── auth
│── utils
```

This structure improves maintainability, scalability, and code organization.

---

## 🔐 Security Implementation

* BCrypt password hashing for secure credential storage
* JWT token validation on every protected request
* Refresh token verification with expiry checks
* Role-based access permissions
* Stateless authentication flow

---

## 📡 API Endpoints

| Method | Endpoint                | Description                           |
| ------ | ----------------------- | ------------------------------------- |
| POST   | `/auth/v1/signup`       | Register a new user                   |
| POST   | `/auth/v1/login`        | Authenticate user and generate tokens |
| POST   | `/auth/v1/refreshToken` | Generate new access token             |
| GET    | `/ping`                 | Health check                          |

---

## 🔄 Authentication Flow

### Login

1. User submits credentials
2. Credentials validated using Spring Security
3. JWT Access Token + Refresh Token generated
4. Tokens returned to client

### Token Refresh

1. Client sends refresh token
2. Token validated from database
3. New access token generated

---

## ⚡ Key Learnings

* Spring Security configuration
* JWT authentication flow
* Secure password handling
* REST API design
* Stateless backend security systems
* Microservice-ready architecture

---

## 🚀 Future Improvements

* Logout with token revocation
* Redis token storage
* Rate limiting
* Docker deployment
* API Gateway integration
* OAuth2 / Keycloak support

---

## ▶️ Run Locally

```bash id="vq1y72"
git clone https://github.com/vaibhv19/Auth-service.git
cd Auth-service
./mvnw spring-boot:run
```

---

## 👨‍💻 Author
Vaibhav Gupta

Developed as part of backend engineering and microservices learning journey.
