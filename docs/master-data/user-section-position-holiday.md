# Master Data: User, Section, Position & Holiday

This module configures the human resources, organizational structure, access control, and manufacturing calendar of CASTEM Philippines.

---

## 1. User Management (`User`)

Manages user accounts, authentication credentials, assigned roles, and organizational affiliations.

* **Key Attributes**:
  * `id`: Unique user identifier (UUID).
  * `username`: Corporate login account identifier.
  * `fullName` / `firstName` / `lastName`: User identification names.
  * `email`: Corporate email used for notifications and account recovery.
  * `sectionId`: Linked organizational department (`Section`).
  * `positionId`: Linked job title and authority rank (`Position`).
  * `role`: System access level (Administrator, Production Planner, Quality Inspector, Warehouse Operator, Sales Officer).
  * `status`: Active or Inactive.

---

## 2. Section (`Section`)

Defines functional factory departments and cost centers within the plant.

* **Key Attributes**:
  * `code`: Section code (e.g., `CAST`, `MCH`, `QA`, `WH`, `ENG`).
  * `name`: Department name (e.g., Casting Section, Machining Section, Quality Assurance, Warehouse).
  * `description`: Department scope and operational responsibilities.
* **Operational Usage**:
  * Routing of scrap tickets, defective lot investigation, and task assignment on the shop floor.

---

## 3. Position (`Position`)

Represents job titles, rank hierarchies, and operational sign-off authorities.

* **Key Attributes**:
  * `title`: Job position title (e.g., Operator, Supervisor, Production Engineer, Department Manager).
  * `level`: Seniority and authority level.
  * `description`: Position responsibilities.
* **Operational Usage**:
  * Used in quality approval gates, early-start authorization workflows, and inspection sign-offs.

---

## 4. Holiday & Working Calendar (`Holiday`)

Defines national holidays, local holidays, and company plant shutdown days.

* **Key Attributes**:
  * `date`: Calendar date.
  * `name`: Holiday name (e.g., New Year's Day, Independence Day, Annual Plant Maintenance).
  * `type`: Regular Holiday, Special Non-Working Day, or Company Scheduled Downtime.
  * `isWorkingDay`: Boolean flag indicating if production shifts are active.
* **Operational Usage**:
  * **Lead Time & Scheduler Calculation**: Directly utilized by the **Casting Plan Scheduler** and **Production Plan Scheduler** to compute accurate Estimated Completion Dates (ECD) and Estimated Time of Departure (ETD), skipping non-working days.
