# 🔬 Research Laboratory Management System (LabRMS) – Full Stack Application

This project is a complete, modular **Research Laboratory Management System (LabRMS)** developed using **Angular** for the modern frontend experience and a suite of **Spring Boot microservices** for a scalable, robust backend. It is designed to be the single source of truth for all essential laboratory operations, managing **members**, **equipment**, **events**, and **publications** through an intuitive web interface.

## ✨ Features & Modules

LabRMS provides comprehensive management capabilities across key lab domains:

* **👥 Member Management:** Track lab personnel, roles, contact information, and project assignments.
* **🛠️ Equipment/Tool Management:** Catalog, assign usage, and monitor the status of all laboratory equipment.
* **🗓️ Event Management:** Schedule and manage lab meetings, seminars and training sessions.
* **📚 Publication Management:** Centralize records of all research outputs, including paper details, authors, and associated projects.

---

## 📐 Project Architecture
├── laboratory_backend_springboot/ # Backend Microservices (Spring Boot, Maven)
│   ├── config-service
│   ├── registry-service
│   ├── gateway
│   ├── membre-service
│   ├── outil-service
│   ├── evenement-service
│   └── publication-service
└── laboratory_frontend_angular/ # Frontend Application (Angular, TypeScript)

---

## 🎨 Frontend – Angular Application

**Path:** `laboratory_frontend_angular/`

The frontend is a **Single Page Application (SPA)** built with **Angular** and styled using **Angular Material** for a responsive, modern user experience. It consumes data from the backend microservices via a dedicated **API Gateway**.

### Prerequisites

* **Node.js** (LTS recommended)
* **npm** (Node Package Manager) or **Yarn**

### Run the Frontend

1.  Navigate into the frontend directory:
    ```bash
    cd laboratory_frontend_angular
    ```
2.  Install dependencies:
    ```bash
    npm install
    ```
3.  Start the development server:
    ```bash
    ng serve
    ```

The application will be available at: **http://localhost:4200**

---

## ⚙️ Backend – Spring Boot Microservices

**Path:** `laboratory_backend_springboot/`

The backend is composed of independent **Spring Boot** services managed by **Maven**. Key components of the architecture include:

### Core Infrastructure Services

| Service Name | Technology/Role | Description |
| :--- | :--- | :--- |
| **`config-service`** | **Spring Cloud Config** | Centralized, version-controlled configuration for all microservices (e.g., database credentials, service URLs). |
| **`registry-service`** | **Eureka Server** | Service Discovery. Allows services to register themselves and locate others without hardcoding hostnames/ports. |
| **`gateway`** | **Spring Cloud Gateway** | API Gateway. Acts as the single entry point for the frontend, handling routing, security (authentication/authorization), and cross-cutting concerns. |

### Domain Services

| Service Name | Domain | Persistence |
| :--- | :--- | :--- |
| **`membre-service`** | Laboratory Members | Manages member profiles and roles. |
| **`outil-service`** | Equipment and Tools | Handles equipment inventory and status. |
| **`evenement-service`** | Events Management | Schedules and tracks lab events and meetings. |
| **`publication-service`** | Publication Records | Stores metadata for research papers and publications. |

### Prerequisites

* **Java 17+** (Required for Spring Boot 3)
* **Maven** (Included wrapper `./mvnw` is recommended)
* **Database:** A relational database (e.g., **PostgreSQL, MySQL**) for persistent services.

### Run a Backend Service

The infrastructure services (`config-service`, `registry-service`, `gateway`) **must be started first**.

1.  Navigate to the service directory:
    ```bash
    cd laboratory_backend_springboot/<service-name>
    ```
2.  Run the application using the Maven wrapper:
    ```bash
    ./mvnw spring-boot:run
    ```

**Pro-Tip:** For local development, consider using an IDE like **IntelliJ IDEA** to easily run multiple services simultaneously.