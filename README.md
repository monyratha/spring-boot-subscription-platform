# Spring Boot Subscription Platform

A modular, microservices-based SaaS platform built with Spring Boot 3.5.4 and Spring Cloud 2023.x. This system allows users to register, manage their own subdomain-based sites, choose subscription plans, and access features based on role-based permissions.

---

## 🧱 Project Modules

| Module             | Description |
|--------------------|-------------|
| `auth-service`     | Handles user authentication (login, register, JWT issuance, password hashing) |
| `user-service`     | Manages users, profiles, roles, permissions, and referral/invite codes |
| `site-service`     | Manages customer sites (subdomains), ownership, and multi-tenant logic |
| `subscription-service` | Handles subscription plans, active plans, history, billing, etc. |
| `config-service`   | Centralized Spring Cloud Config Server (Git-backed) |
| `gateway-service`  | API Gateway using Spring Cloud Gateway + route-based authentication |
| `discovery-service`| Eureka server for service discovery |
| `audit-log-service`| Tracks and stores all important user/system actions |
| `settings-service` | Platform-wide configuration and environment flags |

---

## 🚀 Development Plan

### ✅ Phase 1: Infrastructure Setup
- [x] Create parent Maven project (`spring-boot-subscription-platform`)
- [x] Add `auth-service` as module
- [ ] Create and register `config-service`
- [ ] Add `discovery-service` (Eureka)
- [ ] Implement Docker Compose to launch all services locally

### 🧩 Phase 2: Core Features
- [x] Generate `auth-service` via Spring Initializr
- [ ] Configure Config Server and connect `auth-service`
- [ ] Implement login, register, password hashing, JWT generation
- [ ] Add role & permission model
- [ ] Implement global error handling, validation, Swagger

### 🧑‍💼 Phase 3: User & Tenant Services
- [ ] Create `user-service` and link with `auth-service`
- [ ] Build `site-service` to manage subdomains & ownership
- [ ] Add user-site assignment logic
- [ ] Start `subscription-service` with plan models and history tracking

### 📊 Phase 4: Advanced Features
- [ ] Implement role-based access control with permissions
- [ ] Add audit logging and user actions
- [ ] Connect Prometheus/Grafana for observability
- [ ] Add centralized logging with ELK or Loki

---

## 🛠️ Tech Stack

- **Java 17**
- **Spring Boot 3.5.4**
- **Spring Cloud 2023.0.1**
- **Spring Security + JWT**
- **Spring Data JPA**
- **Eureka Service Discovery**
- **Spring Cloud Gateway**
- **Spring Cloud Config Server**
- **Docker / Docker Compose**
- **MySQL / PostgreSQL / Redis**
- **Prometheus + Grafana**
- **OpenAPI / Swagger**

---

## 📂 Folder Structure (Monorepo)

```azure
spring-boot-subscription-platform/
├── pom.xml # Parent POM
├── auth-service/ # First service (login/register/jwt)
├── config-service/ # Spring Cloud Config Server
├── discovery-service/ # Eureka
├── user-service/ # User management & RBAC
├── site-service/ # Subdomain management
├── subscription-service/ # Plan logic
├── docker/ # Docker Compose setup
└── config-repo/ # Git-backed external config files
```


---

## 🔐 Roles & Permissions Overview

| Role         | Description |
|--------------|-------------|
| `Admin`      | Full platform access |
| `Sub-admin`  | Manage subscriptions and customers |
| `Marketing`  | Promote via referral/invite codes |
| `Customer`   | Owns and manages sites, products, services |
| `Sub-user`   | Assists customer in site/product/category management |

---

## ✨ Goals

- Clean microservices separation
- Multi-tenant architecture using subdomains
- Secure, scalable, and extensible
- Production-ready with observability, logging, and CI/CD

---

## 🧠 Author

Built and maintained by **Lucas** — a backend developer passionate about scalable SaaS, clean code, and great architecture.

