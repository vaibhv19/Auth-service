# Auth Service

A Spring Boot-based authentication service that provides user signup, login, JWT token generation, refresh-token handling, and stateless security using Spring Security.

## Overview

This project is a backend authentication starter built with:

- Java 21
- Spring Boot 3.2
- Spring Security
- Spring Data JPA
- MySQL
- JWT (JSON Web Tokens)
- Gradle

It is designed as a simple but practical auth service for learning, prototyping, or building on top of a microservice-style architecture.

## What This Service Does

The current implementation supports:

- User registration through the signup endpoint
- User authentication through login
- JWT access-token generation
- Refresh-token creation and validation
- Password hashing with BCrypt
- Stateless request authentication using a custom JWT filter

## Project Structure

```text
app/
├── src/
│   ├── main/
│   │   ├── java/authservice/
│   │   │   ├── auth/            # Security, JWT filter, password config
│   │   │   ├── controller/      # Auth and token endpoints
│   │   │   ├── entities/        # User, role, refresh-token models
│   │   │   ├── model/           # DTOs for user input/output
│   │   │   ├── repository/      # Data access interfaces
│   │   │   ├── request/         # Request payload classes
│   │   │   ├── response/        # Response payload classes
│   │   │   └── service/         # JWT, refresh token, user details logic
│   │   └── resources/          # Application resources
│   └── test/
├── build.gradle
└── gradlew
```

## Main Endpoints

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | /auth/v1/signup | Registers a new user and returns tokens |
| POST | /auth/v1/login | Authenticates a user and returns tokens |
| POST | /auth/v1/refreshToken | Validates a refresh token and issues a new access token |

## Authentication Flow

1. A client sends credentials to the login endpoint.
2. Spring Security validates the user.
3. The service creates a refresh token and issues a JWT access token.
4. The client sends the JWT in the Authorization header for protected requests.
5. The custom JWT filter validates the token before the request continues.

## Prerequisites

Before running the project, make sure you have:

- Java 21 installed
- Gradle or the included Gradle wrapper
- A MySQL database running

## Configuration

This project uses Spring Data JPA and expects a database configuration to be present in the application properties file.

Create an application configuration file such as:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/auth_service
spring.datasource.username=your_username
spring.datasource.password=your_password
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

Place it in:

```text
app/src/main/resources/application.properties
```

## Running the Application

From the project root:

```bash
./gradlew :app:bootRun
```

Or, if you are using Windows:

```powershell
gradlew.bat :app:bootRun
```

## Building the Project

```bash
./gradlew :app:build
```

## Notes

- The project contains domain models for roles, although the current signup flow creates users without assigning explicit roles.
- The JWT secret is currently hardcoded in the JWT service class. For production use, this should be moved to environment variables or a secure configuration source.
- This service is a solid foundation for extending into a more complete identity platform with logout, password reset, email verification, and role-based authorization rules.

## Author

Vaibhav Gupta
