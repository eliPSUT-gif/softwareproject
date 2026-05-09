# Flight Booking System

---

## 1. Group Info

| Field | Details |
|---|---|
| **Group Number** | Group 09 |
| **Case Study** | Flight Booking System |
| **Course** | Software Engineering - Winter 2026 |
| **Instructor** | Samer ElKababji |

### Team Members

| Name | Student ID |
|---|---|
| Elias Hreish | 20220677 |
| Ghaith Hajarat | 20220445 |
| Faris Samara | 20220553 |
| Ahmad Abed | 20220976 |

---

## 2. Overview

### System Purpose
A web-based and database-driven platform that enables users to search, book, and manage flight reservations. Customers can browse available flights, select seats, make online payments, and receive electronic tickets. Airline administrators manage flight schedules and seat availability, while system administrators monitor users and system settings.

### Tools Used
- PlantUML - UML and C4 diagram source files
- Draw.io - Supplementary diagram editing
- Visual Studio Code - Primary IDE
- Git / GitHub - Version control and collaboration
- Pandoc - Markdown to PDF conversion

---

## 3. Diagrams

| Diagram | File | Description |
|---|---|---|
| C4 Level 1 - Context | `uml/c4_context.puml` | Shows the system boundary and external actors/systems |
| C4 Level 2 - Container | `uml/c4_container.puml` | Shows internal containers such as web app, API server, database, and services |
| Activity Diagram with Swimlanes | `uml/activity_swimlane.puml` | Shows the booking workflow across Customer, System, and Payment Gateway |
| Use Case Diagram | `uml/use_case.puml` | Shows system use cases for Customer, Airline Admin, and System Admin |
| High-Level Sequence Diagram | `uml/sequence_highlevel.puml` | Shows stakeholder-level flight booking interaction |
| Detailed Sequence Diagram | `uml/sequence_detailed.puml` | Shows developer-level API, database, payment, and notification flow |
| Class Diagram | `uml/class_diagram.puml` | Shows system classes, attributes, operations, associations, inheritance, aggregation, and composition |
| DFD Level 1 | `uml/dfd_level1.puml` | Shows data flow between users, processes, data stores, and external systems |

---

## 4. Repo Structure

```text
/
├── README.md
├── docs/
│   ├── report.md
│   └── se_report_group_09.pdf
└── uml/
    ├── c4_context.puml / c4_context.png
    ├── c4_container.puml / c4_container.png
    ├── activity_swimlane.puml / activity_swimlane.png
    ├── use_case.puml / use_case.png
    ├── sequence_highlevel.puml / sequence_highlevel.png
    ├── sequence_detailed.puml / sequence_detailed.png
    ├── class_diagram.puml / class_diagram.png
    └── dfd_level1.puml / dfd_level1.png
```

---

## 5. Contributions

| Member | Role | Commits |
|---|---|---|
| Elias Hreish | C4 context diagram, C4 container diagram, and architecture review | 1 |
| Ghaith Hajarat | Use case diagram, use case descriptions, and interaction review | 1 |
| Faris Samara | High-level sequence diagram, detailed sequence diagram, and final report organization | 1 |
| Ahmad Abed | Activity diagram, class diagram, DFD, README, and final documentation review | 1 |
