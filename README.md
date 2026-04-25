# Flight Booking System

---

## 1. Group Info

| Field | Details |
|---|---|
| **Group Number** | Group 09 |
| **Case Study** | Flight Booking System |
| **Course** | Software Engineering – Winter 2026 |
| **Instructor** | Samer ElKababji |

### Team Members

| Name 		| Student ID |
|-------|-------|
| Elias Hreish	 | 20220677 |
| Ghaith Hajarat | 20220445 |
| Faris Samara   | 20220553 |
| Ahmad Abed     | 20220976 |

---

## 2. Overview

### System Purpose
A web-based and database-driven platform that enables users to search, book, and manage flight reservations. The system allows customers to browse available flights, select seats, make online payments, and receive electronic tickets. Airlines and administrators can update flight schedules, manage seat availability, and track booking statistics in real time.

### Tools Used
- **PlantUML** – UML and C4 diagram generation
- **Draw.io** – Supplementary diagram editing
- **Visual Studio Code** – Primary IDE
- **Git / GitHub** – Version control and collaboration
- **Pandoc** – Markdown to PDF conversion

---

## 3. Diagrams

| Diagram | File | Description |
|---|---|---|
| C4 Level 1 – Context | `uml/c4_context.puml` | Shows the system and all external actors/systems it interacts with |
| C4 Level 2 – Container | `uml/c4_container.puml` | Shows internal containers (web app, API, database, services) |
| Activity Diagram (Swimlanes) | `uml/activity_swimlane.puml` | High-level booking process across Customer, System, and Payment Gateway |
| Use Case Diagram | `uml/use_case.puml` | All system use cases for Customer, Airline Admin, and System Admin |
| Sequence Diagram – High Level | `uml/sequence_highlevel.puml` | Stakeholder-level interaction for the flight booking flow |
| Sequence Diagram – Detailed | `uml/sequence_detailed.puml` | Developer-level technical interaction with API calls and DB operations |

---

## 4. Repo Structure

```
/
├── README.md                  # This file (also serves as report title page)
├── docs/
│   ├── report.md              # Full project report in Markdown
│   └── report.pdf             # Final compiled PDF report
└── uml/
    ├── c4_context.puml        # C4 Level 1 – Context Diagram
    ├── c4_container.puml      # C4 Level 2 – Container Diagram
    ├── activity_swimlane.puml # Activity Diagram with swimlanes
    ├── use_case.puml          # Use Case Diagram
    ├── sequence_highlevel.puml# High-level Sequence Diagram
    └── sequence_detailed.puml # Detailed Sequence Diagram
```

---

## 5. Contributions

| Member | Role | Commits |
|---|---|---|
| [Member 1] | [e.g., C4 Diagrams, Report] | [N] |
| [Member 2] | [e.g., Use Case + Sequence Diagrams] | [N] |
| [Member 3] | [e.g., Activity Diagram, README] | [N] |
| [Member 4] | [e.g., System Description, Review] | [N] |
