# Job Tracker Backend (Spring Boot + Kafka)

A backend service for tracking job applications and managing the full application lifecycle, built with Spring Boot and PostgreSQL. The system uses event-driven architecture with Kafka to process asynchronous workflows such as application analysis.

---

## 🚀 Overview

This application allows users to:

* Manage job applications (CRUD)
* Track application status progression
* Store notes and interview details
* View application history
* Process asynchronous workflows using Kafka

The focus of this project is backend architecture, API design, and scalable system design.

---

## 🧱 Tech Stack

* **Java 17**
* **Spring Boot 3**
* **Spring Web**
* **Spring Data JPA (Hibernate)**
* **PostgreSQL**
* **Apache Kafka**
* **Lombok**
* **JUnit 5 / Mockito (planned)**

---

## 📦 Features

### ✅ Core Features

* User authentication (JWT) *(planned)*
* Job application management
* Status tracking (Applied → Offer/Rejected)
* Notes and interview tracking *(planned)*
* Application history (audit log)

### ⚡ Event-Driven Processing

* Publish event when application is created
* Kafka consumer processes application asynchronously
* Generates analysis (e.g. backend/frontend match, priority score)
* Stores analysis result in database

---

## 🧩 Architecture

The project follows a layered architecture:

* **Controller** → REST endpoints
* **Service** → business logic
* **Repository** → database access
* **Entity** → persistence model
* **DTO** → request/response objects
* **Messaging** → Kafka producer/consumer

---

## 📂 Project Structure

```text
src/main/java/com/renhan/jobtracker/
├── controller/
├── service/
├── repository/
├── entity/
├── dto/
├── messaging/
├── security/
├── config/
├── exception/
```

---

## 🗄️ Core Domain

### JobApplication

* companyName
* roleTitle
* jobUrl
* location
* status
* createdAt / updatedAt

### ApplicationStatus

* APPLIED
* OA
* INTERVIEW
* OFFER
* REJECTED

---

## 🔌 API Endpoints (MVP)

### Applications

* `POST /api/applications`
* `GET /api/applications`
* `GET /api/applications/{id}`

---

## ⚙️ Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-username/job-tracker-backend.git
cd job-tracker-backend
```

### 2. Start PostgreSQL

Make sure PostgreSQL is running locally:

```sql
CREATE DATABASE job_tracker;
```

### 3. Configure application.yml

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/job_tracker
    username: postgres
    password: postgres
```

### 4. Run the application

```bash
./mvnw spring-boot:run
```

---

## 🧪 Example Request

### Create Job Application

```http
POST /api/applications
```

```json
{
  "companyName": "AdventHealth",
  "roleTitle": "Software Engineer",
  "jobUrl": "https://example.com/job/123",
  "location": "Orlando, FL"
}
```

---

## 📈 Future Improvements

* JWT Authentication (Spring Security)
* Kafka retry / dead-letter handling
* Pagination & filtering
* OpenAPI / Swagger docs
* Redis caching
* Docker + Docker Compose
* Deployment (AWS / Render)

---

## 💡 Design Considerations

* Clean separation of concerns (controller/service/repository)
* Event-driven architecture for async workflows
* Extensible design for future frontend integration
* Focus on maintainability and scalability

---

## 👤 Author

Renhan Huai
Software Engineer (Full-Stack, Distributed Systems)

* Java / Spring Boot
* Angular
* Event-driven architecture
* Distributed systems

---

## 📌 Notes

This project is designed as a backend-focused system to demonstrate:

* API design
* data modeling
* asynchronous processing
* system architecture

It reflects real-world backend patterns used in enterprise applications. 
