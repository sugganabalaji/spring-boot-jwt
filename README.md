# Spring Boot JWT Authentication Project
## 📌 Overview
This project implements a secure REST API backend using Spring Boot, Spring Data JPA, PostgreSQL, and Lombok, with JWT (`JSON Web Token`) for authentication and authorization.
It provides user registration, login, and role-based access control, serving as a foundation for modern web applications.

## 🚀 Tech Stack
- Spring Boot MVC – REST API framework
- Spring Data JPA – ORM and database access
- PostgreSQL – Relational database
- Lombok – Boilerplate code reduction
- JWT – Stateless authentication

## ⚙️ Features
- User registration and login with JWT authentication
- Role-based authorization (`USER`, `ADMIN`)
- Secure REST endpoints with token validation
- PostgreSQL integration via JPA/Hibernate
- Clean code with Lombok annotations

## 📂 Project Structure
```markdown
    src/**
    └── main/
    ├── java/
    │   └── com.app
    │       ├── model/         # JPA Entities
    │       ├── controller/    # REST Controllers
    │       ├── service/       # Business Logic
    │       ├── repository/    # Spring Data JPA Repositories
    │       ├── config/        # Security & JWT configuration
    │       └── SpringBootJwtApplication.java # Entry point
    └── resources/
            └── application.yaml
```

### 🛠️ Setup Instructions
**1. 	Clone the repository**
```bash
    git clone https://github.com/sugganabalaji/spring-boot-jwt.git
    cd spring-boot-jwt
```

**2. Configure PostgreSQL**
- Create a Shcema (e.g., `Dev`)
- Update `application.yaml` with database credentials
```yaml
    spring.datasource.url=jdbc:postgresql://localhost:5432/Dev
    spring.datasource.username=postgres
    spring.datasource.password=root
    spring.jpa.hibernate.ddl-auto=update
```

**3. 	Build and run**
```bash
  mvn clean install
  mvn spring-boot:run
```

### 🔑 API Endpoints
- POST /user/register → Register new user
- POST /user/login → Authenticate & get JWT
- GET / → Get Ok message
- GET /students → Get Students details

### 🧪 Testing
- Use **Postman** to test endpoints.
- Include JWT in `Authorization` header:
```
    Authorization: Bearer <token>
```

### 📖 Example JWT Flow
1. 	Register a new user → Store User to DB with encoded JWT token
2. 	Login → receive JWT token
3. 	Access protected endpoints with token

### 🔎 Understanding JWTs with [jwt.io](https://jwt.io/)
When working with `JSON Web Tokens (JWT)`, it’s often useful to inspect and debug the tokens your application generates. The site [jwt.io](https://www.jwt.io/) provides a free, interactive tool where you can:
- **Decode JWTs**: Paste a token to view its header, payload, and signature in human‑readable form.
- **Verify signatures**: Check if the token is correctly signed using your secret or public key.
- **Experiment with claims**: Add or modify claims (like `sub`, `exp`, `roles`) to understand how they affect authentication.
- **Learn the structure**: JWTs are composed of three parts — header, payload, and signature — all base64‑encoded.
#### Example Workflow
- Generate a JWT by logging in to your Spring Boot app.
- Copy the token from the response header or body.
- Paste it into [jwt.io](https://jwt.io/).
- Inspect the claims (e.g., `username`, `roles`, `expiry`).
- Verify the signature using your secret key to ensure integrity.


### ✅ Future Enhancements
- Refresh tokens for extended sessions
- Password reset via email
- Swagger/OpenAPI documentation