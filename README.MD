# Spring Boot Taskify Web Application

## Overview
This is a simple **Todo Web Application** built using **Spring Boot, Spring Security, Spring Data JPA, and Thymeleaf**. The application allows users to:
- Add, update, and delete todo items.
- Use in-memory authentication with Spring Security.
- Store todo items in an H2 database.

## Features
- **User Authentication**: Uses Spring Security with in-memory authentication.
- **CRUD Operations**: Users can create, update, and delete their todo items.
- **Session Management**: Maintains session attributes for user interactions.
- **Database Integration**: Uses **H2 Database** (or an in-memory list for non-JPA version).
- **Thymeleaf Template Engine**: Used for rendering UI pages.

---

## Technologies Used
- Java 17+
- Spring Boot 3+
- Spring Security
- Spring Data JPA
- Thymeleaf
- H2 Database
- Maven

---

## Project Structure
```
myfirstwebapp/
│── src/main/java/com/skverma/springboot/myfirstwebapp/
│   ├── security/
│   │   ├── SpringSecurityConfiguration.java
│   ├── todo/
│   │   ├── Todo.java
│   │   ├── TodoController.java
│   │   ├── TodoControllerJpa.java
│   │   ├── TodoRepository.java
│   │   ├── TodoService.java
│── src/main/resources/
│   ├── templates/
│   │   ├── listTodos.html
│   │   ├── todo.html
│   ├── application.properties
│── pom.xml
│── README.md
```

---

## Getting Started
### 1. Clone the Repository
```sh
git clone https://github.com/your-repo-url.git
cd myfirstwebapp
```

### 2. Configure Application Properties
Modify `src/main/resources/application.properties`:
```properties
spring.h2.console.enabled=true
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.jpa.database-platform=org.hibernate.dialect.H2Dialect
```

### 3. Build and Run the Application
Use Maven to build and run the application:
```sh
mvn spring-boot:run
```

The application will be available at: **`http://localhost:8080/list-todos`**

---

## Security Configuration
- The `SpringSecurityConfiguration.java` file configures in-memory authentication.
- Default users:
  - Username: **sourav**, Password: **dummy**
  - Username: **verma**, Password: **dummy**

To change passwords, update the method:
```java
@Bean
public PasswordEncoder passwordEncoder(){
    return new BCryptPasswordEncoder();
}
```

---

## API Endpoints
| HTTP Method | Endpoint       | Description                 |
|------------|---------------|-----------------------------|
| GET        | `/list-todos`  | Display all todos           |
| GET        | `/add-todo`    | Show add todo form          |
| POST       | `/add-todo`    | Add a new todo              |
| GET        | `/update-todo` | Show update todo form       |
| POST       | `/update-todo` | Update an existing todo     |
| GET        | `/delete-todo` | Delete a todo by ID         |

---

## H2 Database Console
You can access the **H2 database** console at:
```
http://localhost:8080/h2-console
```
Use the same JDBC URL as configured in `application.properties`.

---

## Contribution
Feel free to fork this repository, create a feature branch, and submit a pull request!

