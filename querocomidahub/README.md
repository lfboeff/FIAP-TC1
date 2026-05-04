# Quero Comida Hub

**Tech Challenge 1 - Pós-graduação em Arquitetura e Desenvolvimento Java - FIAP**

A REST API backend for managing users and restaurant owners on a food delivery platform. Supports user registration, authentication, address management, and password management.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Language | Java 21 |
| Framework | Spring Boot 3.5 |
| Database | MySQL 8.4 |
| Data Access | Spring JdbcClient (no ORM) |
| Migrations | Flyway |
| Documentation | SpringDoc OpenAPI (Swagger UI) |
| Security | spring-security-crypto (BCrypt) |
| Containerization | Docker + Docker Compose |

---

## Getting Started

**Prerequisites:** Docker and Docker Compose installed.

```bash
# Clone the repository
git clone https://github.com/lfboeff/FIAP.git
cd "FIAP/Fase 1/0. Tech Challenge/querocomidahub"

# Build and start the containers
docker compose up --build
```

Once running, the following URLs are available:

| Resource | URL |
|---|---|
| API base | http://localhost:8080/api/v1 |
| Swagger UI | http://localhost:8080/swagger-ui.html |
| Health check | http://localhost:9090/actuator/health |

To stop:
```bash
docker compose down
```

To stop and remove all data:
```bash
docker compose down -v
```

---

## API Endpoints

All endpoints are prefixed with `/api/v1`.

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/users` | List all users. Supports optional `?name=` filter. |
| `POST` | `/users` | Create a new user with address. |
| `PUT` | `/users/{id}` | Update user data (name, email, login, type). |
| `DELETE` | `/users/{id}` | Permanently delete a user and their address. |
| `PUT` | `/users/{id}/address` | Replace a user's address. |
| `PATCH` | `/users/{id}/password` | Change password (requires current password). |
| `POST` | `/users/login` | Validate credentials and return user profile. |

Full request/response examples are available in the Swagger UI.

---

## Postman Collection

A ready-to-import Postman collection is available at:

```
postman/querocomidahub.postman_collection.json
```

It contains **11 happy path** and **23 error path** scenarios, pre-configured for `http://localhost:8080/api/v1`.

---

## Author

| Name | RM |
|---|---|
| Luis Felipe Boeff | RM372311 |
