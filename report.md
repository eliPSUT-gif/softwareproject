# Software Engineering Project Report
## Group 09 – Flight Booking System

---

## 1. System Description

The **Flight Booking System** is a web-based and database-driven platform that enables users to search, book, and manage flight reservations online. The system connects customers, airlines, and payment providers in a unified digital ecosystem.

Customers can browse available flights, select seats, enter passenger information, make secure online payments, and receive electronic tickets. Airline administrators can update flight schedules, manage seat availability, and track real-time booking statistics. System administrators oversee user management and platform configuration.

The system maintains a central database containing flight records, passenger data, seat maps, booking histories, and transaction records. Integration with external payment gateways (e.g., Stripe), notification services (e.g., SendGrid), and airline databases ensures accurate, up-to-date, and reliable operations.

---

## 2. C4 Model – Level 1: Context Diagram

The context diagram shows the Flight Booking System as a single unit and identifies all external actors and systems it interacts with.

**Actors:**
- **Customer** – Searches and books flights, makes payments, manages reservations.
- **Airline Administrator** – Manages flights, schedules, and seat availability.
- **System Administrator** – Manages users and configures system settings.

**External Systems:**
- **Payment Gateway** – Processes online payments and refunds.
- **Notification Service** – Sends e-tickets and confirmations via email/SMS.
- **Airline Database** – External data source for real-time flight schedules.

![C4 Context Diagram](../uml/c4_context.png)

---

## 3. C4 Model – Level 2: Container Diagram

The container diagram breaks the Flight Booking System into its internal deployable units.

| Container | Technology | Responsibility |
|---|---|---|
| Web Application | React.js | Customer-facing UI for search and booking |
| Admin Portal | React.js | UI for airline and system administrators |
| API Server | Node.js / REST | Core business logic and orchestration |
| Database | PostgreSQL | Persistent storage for all system data |
| Notification Service | Node.js / Mailer | Generates and dispatches e-tickets |
| Airline Data Sync Service | Python / Scheduler | Syncs flight data from external airline DB |

![C4 Container Diagram](../uml/c4_container.png)

---

## 4. Activity Diagram with Swimlanes

The activity diagram models the end-to-end flight booking process across three swimlanes: **Customer**, **Flight Booking System**, and **Payment Gateway**.

The flow begins with the customer searching for flights, continues through seat selection and passenger detail entry, then moves into payment processing. On success, the system confirms the booking and sends an e-ticket. On failure, reserved seats are released and the customer is notified.

![Activity Diagram](../uml/activity_swimlane.png)

---

## 5. Use Case Diagram

The use case diagram identifies all interactions between actors and the system.

![Use Case Diagram](../uml/use_case.png)

---

## 6. Use Case Descriptions

### UC-01: Search Flights

| Field | Description |
|---|---|
| **Use Case ID** | UC-01 |
| **Name** | Search Flights |
| **Actor** | Customer |
| **Precondition** | Customer is on the search page (login not required) |
| **Trigger** | Customer enters search parameters and submits |
| **Main Flow** | 1. Customer enters origin, destination, travel date, and number of passengers. 2. System validates inputs. 3. System queries the database for matching available flights. 4. System returns a list of matching flights with prices and durations. 5. Customer browses results. |
| **Alternative Flow** | If no flights are found, system displays a "No flights available" message. |
| **Postcondition** | A list of available flights is displayed to the customer. |

---

### UC-02: Book Flight

| Field | Description |
|---|---|
| **Use Case ID** | UC-02 |
| **Name** | Book Flight |
| **Actor** | Customer |
| **Precondition** | Customer is logged in and has selected a flight from search results |
| **Trigger** | Customer clicks "Book" on a selected flight |
| **Main Flow** | 1. System displays seat map for selected flight. 2. Customer selects available seat(s). 3. Customer enters passenger details (name, passport, contact). 4. System validates details and calculates total price. 5. System presents booking summary. 6. Customer confirms. 7. System temporarily reserves seat(s). 8. System redirects to payment. |
| **Alternative Flow** | If selected seat becomes unavailable, system prompts customer to choose another seat. |
| **Postcondition** | Seat(s) are temporarily reserved and customer proceeds to payment. |
| **Includes** | UC-01 (Search Flights), UC-03 (Make Payment) |

---

### UC-03: Make Payment

| Field | Description |
|---|---|
| **Use Case ID** | UC-03 |
| **Name** | Make Payment |
| **Actor** | Customer, Payment Gateway |
| **Precondition** | Booking has been initiated and seat(s) are temporarily reserved |
| **Trigger** | Customer submits payment details |
| **Main Flow** | 1. Customer enters card/payment details. 2. System forwards payment request to Payment Gateway. 3. Payment Gateway processes the transaction. 4. Payment Gateway returns success with transaction ID. 5. System confirms booking and releases e-ticket. |
| **Alternative Flow** | If payment fails, system releases reserved seat(s) and displays failure message. Customer may retry. |
| **Postcondition** | Payment is confirmed, booking is created, and e-ticket is generated. |

---

### UC-04: Cancel Booking

| Field | Description |
|---|---|
| **Use Case ID** | UC-04 |
| **Name** | Cancel Booking |
| **Actor** | Customer |
| **Precondition** | Customer is logged in and has an existing confirmed booking |
| **Trigger** | Customer selects a booking and clicks "Cancel" |
| **Main Flow** | 1. Customer navigates to "My Bookings". 2. Customer selects the booking to cancel. 3. System displays cancellation policy and refund amount. 4. Customer confirms cancellation. 5. System cancels the booking and releases the seat(s). 6. System initiates refund via Payment Gateway (if applicable). 7. System sends cancellation confirmation to customer. |
| **Alternative Flow** | If the flight is within a non-refundable period, system informs customer of no refund and asks for confirmation. |
| **Postcondition** | Booking is cancelled, seat(s) are marked available, and refund is initiated. |

---

### UC-05: Manage Flights

| Field | Description |
|---|---|
| **Use Case ID** | UC-05 |
| **Name** | Manage Flights |
| **Actor** | Airline Administrator |
| **Precondition** | Administrator is logged in to the Admin Portal |
| **Trigger** | Admin accesses the flight management section |
| **Main Flow** | 1. Admin views list of all flights. 2. Admin selects a flight to add, edit, or deactivate. 3. Admin modifies flight details (schedule, seats, price, status). 4. System validates and saves changes. 5. System updates availability across the platform in real time. |
| **Alternative Flow** | If flight has existing bookings, system warns admin before allowing cancellation or significant changes. |
| **Postcondition** | Flight records are updated and reflected to customers in real time. |

---

## 7. Sequence Diagrams

### High-Level Sequence (Stakeholder View)

Shows the interaction between the Customer, the Flight Booking System, the Payment Gateway, and the Airline Database at a conceptual level.

![High-Level Sequence Diagram](../uml/sequence_highlevel.png)

### Detailed Sequence (Developer View)

Shows technical-level interactions including REST API endpoints, database queries, JWT authentication, and payment processing.

![Detailed Sequence Diagram](../uml/sequence_detailed.png)

---

*Report generated for SE Project – Winter 2026 | Group 09*
