# Dayro Moreno — Gol o Asistencia (Project Proposal)

Universidad Nacional de Colombia — Facultad de Ingeniería  
Departamento de Ingeniería de Sistemas y Computación e Industrial  
Date: Monday, October 13, 2025

---

## Overview

"Gol o Asistencia" is a business-oriented social networking platform proposal designed to be the central hub for team collaboration inside organizations. It combines the familiar features of existing enterprise collaboration tools (chat, channels, boards) with integrated work boards, meeting management (video & voice), and a company-internal social forum — all focused on providing an efficient, private, and extensible workspace for enterprises.

The platform aims to offer a competitive open alternative to incumbent corporate offerings by prioritizing modularity (microservices), scalability, and real-time collaboration features tailored to organizational workflows.

---

## Table of Contents

1. Needs  
2. Actors  
3. Main features  
4. Technology stack  
5. Architecture overview  
6. Team and roles   
7. Contribution & contact

---

## 1. Needs

- Address monopoly/lock-in concerns in the enterprise social networking market.
- Provide an integrated platform combining messaging, task boards, meetings, and forums.
- Deliver a customizable, secure environment where organizations can centralize communication and workflows.
- Offer cost-effective, modular alternatives to large vendor solutions while maintaining enterprise-grade features.

---

## 2. Actors

- Client Company (Organization): Purchaser / tenant of the service.  
- End Users (Company Employees & Teams): Daily platform users.  
- Administrator: Manages organization settings, access control, roles.  
- Agile Developer: Contributes to project code and tasks.  
- Agile Team Manager / Scrum Master: Manages team activities and sprints.  
- Enterprise Employee: General platform user participating in communication and work.  
- Custom Roles: Organization-level custom role definitions (external contributors, designers, etc.).  
- Development Team (this team): Implements and maintains platform.  
- Technical Support Team: Supports administrators and users.  
- DevOps Team: Manages deployments, CI/CD, and reliability.

---

## 3. Main features

- User & Group Management
  - Registration, authentication, access control
  - Organization-scoped roles and custom role creation
- Instant Messaging
  - Real-time text messaging (channels, DMs, broadcast channels)
- Groups & Channels
  - Topic-based groups, team channels, announcement channels
- Work Boards
  - Trello/Jira-like interactive boards, task assignment, deadlines, status tracking
- Meeting Management (Video & Voice)
  - Unlimited meetings with integrated calendar and reminders (WebRTC/socket based)
- Forum
  - Company-internal social forum with posts, comments, and group-specific visibility
- Notifications
  - Asynchronous notifications for events, mentions, and reminders
- Security & Data Privacy
  - Organization-scoped data isolation and role-based permissions

---

## 4. Technology stack (microservices approach)

We propose a microservices architecture so each feature can use the most suitable technology.

- User & Group Management
  - Language / Framework: FastAPI (Python)
  - Database: PostgreSQL
  - Reason: Structured data, relations, security, concurrency
- Instant Messaging
  - Language / Framework: Node.js (NestJS)
  - Database: MongoDB
  - Reason: Flexible messaging schema, high-speed operations, horizontal scalability
- Work Boards
  - Language / Framework: FastAPI (Python)
  - Database: PostgreSQL
  - Reason: Clear relational structures for tasks, lists, projects
- Meeting Management (Video & Voice)
  - Language / Framework: Node.js + socket.io
  - Data store / cache: Redis
  - Reason: Dynamic session state, presence, real-time coordination
- Forum
  - Language / Framework: FastAPI (Python)
  - Database: MongoDB
  - Reason: Unstructured social content, posts and comments
- Notifications & Background Jobs
  - Language / Framework: Celery + FastAPI (Python)
  - Data store / broker: Redis
  - Reason: Asynchronous processing for notifications, emails, logs
- Frontend
  - Language / Framework: TypeScript, React (with Astro)
  - Reason: Strong ecosystem, component re-use, performance
- Orchestration & Deployment
  - Docker, Kubernetes
  - Reason: Scalability, fault tolerance, microservice orchestration

---

## 5. Architecture overview

- Microservices per major capability (auth/users, messaging, boards, meetings, forum, notifications).
- Shared infrastructure: API gateway, authentication service (JWT/OAuth), service discovery, centralized logging and monitoring.
- Real-time channels: socket gateways backed by Redis for presence and pub/sub.
- Persistent stores: PostgreSQL for relational domain models; MongoDB for flexible content; Redis for cache/session.
- Deployment: Containerized with Docker, orchestrated by Kubernetes for scaling and reliability.

Note: The team has prepared a diagram describing the full microservice architecture (to be included in the repository as an image/diagram file).

---

## 6. Team members & roles

Project Instructor:  
- Liliana Marcela Olarte Mesa — lmolartem@unal.edu.co

Presenters / Authors:
- Daniel Libardo Diaz González — dandiazgo@unal.edu.co (Product Owner)
- Andres Felipe Leon Sanchez — anleonsa@unal.edu.co (Fullstack developer)
- Juan David Loaiza Reyes — juloaizar@unal.edu.co (Fullstack developer)
- Juan David Chacon Muñoz — juchaconm@unal.edu.co (Scrum Master)
- Javier Santiago Giraldo Jiménez — jgiraldoji@unal.edu.co (Fullstack developer)
- Heric Francisco Vargas Cabiativa — hevargasc@unal.edu.co (Fullstack developer)

Team roles (summary):
- Product Owner: Daniel Libardo Diaz González
- Scrum Master: Juan David Chacon Muñoz
- Fullstack Developers: Javier Santiago Giraldo Jiménez, Juan David Loaiza Reyes, Heric Francisco Vargas Cabiativa, Andrés Felipe León Sánchez

Note: DevOps and other cross-cutting responsibilities will be shared among the entire team as needed.

---

## 7. Contribution & contact

This repository will welcome issues, feature requests, and PRs following a contribution guide (TBD). For questions or to join the project:

Reach out to the Product Owner or any team member listed above via email.

---

## Appendix: University / Course info

Universidad Nacional de Colombia  
Facultad de Ingeniería  
Departamento de Ingeniería de Sistemas y Computación e Industrial

Project delivered: 2025
