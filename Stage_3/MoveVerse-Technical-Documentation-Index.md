# MoveVerse Technical Documentation

## 📖 Overview

This repository contains the technical documentation for **MoveVerse**, a motion-based fitness web application that combines browser-based pose detection using MediaPipe with interactive gameplay mechanics, workout tracking, analytics, and leaderboard systems.

The purpose of this documentation is to provide a structured technical blueprint for the MoveVerse MVP.

---

# 📚 Stage 3: Technical Documentation

## 🎯 Objectives

- Translate project objectives and requirements into a detailed technical plan.
- Define user stories and mockups to clarify functionality.
- Design and document system architecture, backend components, classes, and database structures.
- Create high-level sequence diagrams illustrating interactions between components and services.
- Specify external services and internal API endpoints.
- Plan source control management (SCM) and quality assurance (QA) strategies.
- Justify technical decisions based on scalability, maintainability, and MVP requirements.

---

# 📂 Documentation Sections

## 1. 👤 User Stories and Mockups

### Description
Contains prioritized user stories, UI planning, and application mockups.

### Documents
- [User Stories](./user-stories.md)
- [Mockups](./mockups.md)

---

## 2. 🏗️ System Architecture

### Description
Contains the high-level architecture of MoveVerse, including frontend, backend, MediaPipe integration, and database interactions.

### Documents
- [System Architecture](./system-architecture.md)

---

## 3. ⚙️ Components, Classes, and Database Design

### Description
Defines the internal structure of the MoveVerse system including backend classes, frontend components, and PostgreSQL database schema.

### Documents

#### Frontend
- [React Components Documentation](./react-component.md)

#### Backend
- [Backend Classes Documentation](./backend-classes.md)

#### Database
- [Database Schema and ERD](./database-design.md)

---

## 4. 🔄 Sequence Diagrams

### Description
Illustrates the interaction flow between frontend components, backend APIs, MediaPipe processing, and the PostgreSQL database.

### Documents
- [Sequence Diagrams](./high-level-diagram.md)

---

## 5. 🌐 API Specifications

### Description
Defines external APIs, internal REST API endpoints, request formats, response formats, and authentication flows.

### Documents
- [API Documentation](./api-specifications.md)

---

## 6. 🌱 SCM and QA Strategies

### Description
Defines source control workflows, branching strategies, commit standards, testing plans, and quality assurance methodologies.

### Documents
- [SCM Strategy](./scm-strategy.md)
- [QA and Testing Plan](./qa-testing.md)

---

## 7. 🧠 Technical Justifications

### Description
Explains the reasoning behind major architectural and technical decisions.

### Key Decisions

| Decision | Justification |
|---|---|
| PostgreSQL instead of MongoDB | Strong relational modeling and normalization |
| JWT + Google OAuth | Flexible authentication support |
| Exercise-specific difficulties | Better scalability and exercise balancing |
| Browser-side MediaPipe | Reduced backend processing overhead |
| REST API Architecture | Simpler MVP implementation |
| React + Tailwind CSS | Rapid frontend development |
| Dynamic leaderboard aggregation | Avoids redundant ranking storage |

---

# 📌 Notes

- MoveVerse follows a modular and scalable architecture to support future expansion.
- The current MVP focuses on single-player gameplay with browser-based motion detection.
- Future versions may include multiplayer functionality using Socket.IO and real-time synchronization.

---

# 👥 Team Documentation Responsibilities

| Area | Responsible Member |
|---|---|
| Frontend Components | Frontend Team |
| Backend Architecture | Patrick Macabulos |
| Database Design | Patrick Macabulos |
| MediaPipe Integration | Motion Detection Team |
| Game Logic | Game Development Team |
| QA and Testing | Entire Team |

