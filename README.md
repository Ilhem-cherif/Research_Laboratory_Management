# Laboratory Management System – Full Stack Application

This project is a complete **Research laboratory management system** developed using **Angular** for the frontend and **Spring Boot microservices** for the backend. It is designed to manage laboratory members, equipment, events, and publications through a modern web interface and a scalable backend architecture.

---

## 📁 Project Architecture
├── laboratory_backend_springboot/ # Backend microservices (Spring Boot)
└── laboratory_frontend_angular/ # Frontend application (Angular)
---
## 🎨 Frontend – Angular Application

**Path:** `laboratory_frontend_angular/`  
The frontend provides the user interface of the system and includes:

- Angular components and modules  
- Services for API communication  
- Data models  
- Assets and styles  
- UI design built with **Angular Material**

### Run the Frontend

Make sure Node.js and npm are installed, then:
* cd laboratory_frontend_angular
* npm install
* ng serve

The application will be available at: http://localhost:4200
---
## ⚙️ Backend – Spring Boot Microservices

**Path:** `laboratory_backend_springboot/`  
The backend follows a **microservices architecture** and includes the following services:

- config-service – Centralized configuration  
- registry-service – Service discovery (Eureka)  
- gateway – API Gateway  
- membre-service – Management of laboratory members  
- outil-service – Equipment and tools management  
- evenement-service – Events management  
- publication-service – Publication management  

Each service is an independent Spring Boot application.

### Run a Backend Service

Navigate to any service folder and start it using:
* cd laboratory_backend_springboot/<service-name>
* ./mvnw spring-boot:run