# Todo List REST API Backend

This repository contains the backend implementation of a Todo List application, developed using Java and Spring Boot. It provides a RESTful API to manage task-related operations such as creation, viewing, updating, and deletion.

This project follows modern development practices using Java 17, Spring Boot 3.3.0, and JPA/Hibernate for ORM. It integrates both MySQL and H2 databases, uses Maven for dependency management, and supports frontend integration via REST endpoints and CORS configuration.

---

## Project Objectives

- Develop a clean and modular backend system for managing tasks
- Implement RESTful endpoints following industry best practices
- Build a system easily testable via tools like Postman
- Make the system adaptable to both in-memory and persistent databases
- Design it to be frontend-ready for future integration with React or other frameworks

---

## Technology Stack (Explained)

| Tool / Framework     | Role in Project |
|----------------------|-----------------|
| Java 17              | Primary programming language for all backend logic |
| Spring Boot 3.3.0    | Framework to build, run, and manage the web server with embedded Tomcat |
| Spring Web           | Enables creation of RESTful controllers and endpoint routing |
| Spring Data JPA      | Simplifies database interactions using Java objects instead of SQL directly |
| Hibernate ORM        | Automatically maps Java classes to database tables |
| MySQL                | Used as the primary production database |
| H2 Database          | Lightweight in-memory DB used for local development and testing |
| Maven                | Handles build, dependency management, and project structure |
| Postman              | Used to test and document API endpoints during development |
| CORS Configuration   | Allows integration with frontend applications by enabling cross-origin requests |

---

## Features

- RESTful CRUD APIs for task management
- Modular structure: Controller → Service → Repository
- H2 integration for quick local setup
- MySQL support for persistent storage
- Postman-tested endpoints
- Clean configuration for switching databases
- CORS enabled to support frontend apps like React

---

## How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/Rahul29999/todo-rest-api-springboot.git
cd todo-rest-api-springboot
```

### 2. Start the Application with Maven

```bash
./mvnw spring-boot:run
```

App will be available at: http://localhost:8080

---

## Database Configuration

### Option 1: H2 (In-Memory Database for Testing)

- Default setup uses H2.
- H2 console can be accessed at:  
  http://localhost:8080/h2-console

```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true
```

---

### Option 2: MySQL (Recommended for Production)

1. Make sure MySQL is running locally.
2. Create a database: todoappdb
3. Update application.properties:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/todoappdb
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.jpa.hibernate.ddl-auto=update
```

---

## API Endpoints

| Method | Endpoint                          | Description                   |
|--------|-----------------------------------|-------------------------------|
| GET    | /users/{username}/todos           | Retrieve all todos for a user |
| GET    | /users/{username}/todos/{id}      | Retrieve a specific todo      |
| POST   | /users/{username}/todos           | Create a new todo             |
| PUT    | /users/{username}/todos/{id}      | Update an existing todo       |
| DELETE | /users/{username}/todos/{id}      | Delete a todo                 |

---

## Folder Structure

```
src/
├── main/
│   ├── java/
│   │   └── com/rahul/todo/
│   │       ├── controller/
│   │       ├── service/
│   │       ├── model/
│   │       └── repository/
│   └── resources/
│       ├── application.properties
│       └── data.sql (optional)
└── test/
```

---

## Author

Rahul Kumar Sharma  
B.Tech in Mining Engineering  
IIT (ISM) Dhanbad  
Backend Developer | AI/ML Enthusiast  
GitHub: https://github.com/Rahul29999  
LinkedIn: https://linkedin.com/in/rahul-kumar-sharma-aa0b57233

---

## Future Scope

- Add Spring Security with JWT Authentication
- Implement pagination and sorting
- Add Swagger/OpenAPI documentation
- Write Unit + Integration Tests with JUnit and Mockito
- Dockerize and deploy to Render/AWS

---

## License

This project is open-source and free to use for educational or extension purposes.
